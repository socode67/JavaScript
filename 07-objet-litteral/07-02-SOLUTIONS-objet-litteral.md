# 2. Objet

## Gestion de Tâches

```js

const tasks = [];

let choice;

// CREATION D'UN TEMPLATE DE MESSAGE POUR UNE TACHE
const taskTemplateMessage = (task) => {
  const message = `[ id : ${task.id}, nom : ${task.name}, description : ${
    task.description
  }, terminée : ${task.termine ? "[X]" : "[ ]"}] \n`;
  return message;
};

// AFFICHER LA LISTE DES TACHES
const showTasksList = () => {
  let message = "";
  
  tasks.forEach((task) => {
    message += taskTemplateMessage(task);
  });
  console.log(message);
};

// CREATION DE L'ID D'UNE TACHE
const generateId = () => {
  let id;
  if (tasks.length === 0) {
    id = 1;
  } else {
    const lastIndex = tasks.length - 1;
    const lastTask = tasks[lastIndex];
    id = lastTask.id + 1;
  }

  return id;
};


//CREER UNE TACHE : 
const createTask = (newTask) => {
  const task = {
    id: generateId(),
    ...newTask,
    termine: false,
  };

  tasks.push(task);
  showTasksList();
};


//OBTENIR UNE TÂCHE :
const getTaskById = (id) => tasks.find((task) => task.id === id);


//OBTENIR L'INDEX D'UNE TÂCHE :
const getIndexTask = (id) => {
  return tasks.findIndex((task) => {
    return task.id == id;
  });
};


//MODIFIER UNE TÂCHE :
const editTask = (id, taskEdited, completed = null) => {
  const currentTask = getTaskById(id);

    if (!currentTask) {
    console.log("Erreur : Tâche non trouvée.");
    return;
    }

  let task = {};
  
  if (completed) {
    task = {
      ...currentTask,
      ...taskEdited, 
    };
  } else {
    task = {
      id: currentTask.id,
      ...taskEdited,
    };
  }

  const indexTask = getIndexTask(currentTask.id);
  tasks[indexTask] = task;

  console.log("TACHE MODIFIEE : ", taskTemplateMessage(task));
};


//SUPPRIMER UNE TACHE
const removeTask = (id) => {
  const indexTask = getIndexTask(id);
  const removedTask = tasks[indexTask];

  tasks.splice(indexTask, 1);
  console.log("TACHE SUPPRIMEE : ", taskTemplateMessage(removedTask));
};

//AFFICHER UNE TACHE
const showTaskById = (id) => {
  const task = getTaskById(id);
  const message = taskTemplateMessage(task);
  console.log(message);
};

//AFFICHER LE NOMBRE DE TACHES TERMINEE
const getListCompletedTask = () => {
  const num = tasks.filter((task) => task.termine === true).length;
  console.log(`Tâches terminées : ${num}`);
};

//AFFICHER LE NOMBRE DE TACHES EN COURS
const getListInProgressTask = () => {
  const num = tasks.filter((task) => task.termine === false).length;
  console.log(`Tâches en cours : ${num}`);
};

//AFFICHER MENU
const menu = () => {
  return parseInt(
    prompt(`
    Que souhaitez-vous faire  : 
    1 - Afficher la liste des tâches
    2 - Créer une nouvelle tâche
    3 - Modifier une tâche existante
    4 - Supprimer une tâche
    5 - Marquer une tâche comme terminée
    6 - Afficher une tâche spécifique
    7 - Dupliquer une tâche
    8 - Afficher le nombre de tâches complétées
    9 - Afficher le nombre de tâches à faire
    0 - Quitter le programme
`)
  );
};


//OBTENIR LES ENTRÉES UTILISATEUR :
const getUserInput = (completed = null) => {
  const task = {};
  if (completed) {
    const finir = prompt("Terminé la tâche (o/n):");
    task.termine = finir === "o" ? true : false;
  } else {
    task.name = prompt("Indiquez le nom de la tâche :");
    task.description = prompt("Donnez une description :");
  }

  return task;
};

//DUPPLIQUER UNE TACHE
const duplicateTask = (id) => {
  const taskToDuplicate = getTaskById(id);

  const duplicatedTask = {
    ...taskToDuplicate,
    id: generateId(),
  };
  
  tasks.push(duplicatedTask);

  console.log("TACHE DUPLIQUEE : ", taskTemplateMessage(duplicatedTask));
};

choice =  menu();

while (choice != 0){
 
  
  let id;

  switch (choice) {
    case 1: // Afficher la liste des tâches
      showTasksList();
      break;
    case 2: // Créer une nouvelle tâche
      const newTask = getUserInput();
      createTask(newTask);
      break;
    case 3: // Modifier une tâche existante
      id = Number(prompt("Indiquez l'id de la tâche à modifier : "));
      const taskEdited = getUserInput();
      editTask(id, taskEdited);
      break;
    case 4: // Supprimer une tâche
      id = Number(prompt("Indiquez l'id de la tâche à supprimer : "));
      removeTask(id);
      break;
    case 5: // Marquer une tâche comme terminée
      id = Number(prompt("Indiquez l'id de la tâche terminée : "));
      const completedTask = getUserInput(true);
      editTask(id, completedTask, true);
      break;
    case 6: // Afficher une tâche spécifique
      id = Number(prompt("Indiquez l'id de la tâche à afficher : "));
      showTaskById(id);
      break;
    case 7: //Dupliquer une tâche
      id = Number(prompt("Indiquez l'id de la tâche à dupliquer : "));
      duplicateTask(id);
      break;
    case 8: // Afficher le nombre de tâches complétées
      getListCompletedTask();
      break;
    case 9: // Afficher le nombre de tâches à faire
      getListInProgressTask();
      break;
    case 0: // Afficher le nombre de tâches à faire
      console.log("A bientot");
      break;
    default:
      console.log("Erreur: faire un choix valide");
      break;
  }

  choice =  menu();
};
```