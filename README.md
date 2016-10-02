# mic-webgme
## Project: Task schedule specification with resources usage

The model build with webgme is called task schedule specification with resources usage. 

In the metamodel, the main language contains a folder in which the task scheduling model itself can be instantiated. Task scheduling model contains mainly four parts: a list of tasks to be done, a list of tasks completed, the executor (e.g. CPU) and a list of resources can be gathered system-wide.

In both list of tasks to be done and completed, there is an ordered list of tasks (queue of tasks). All tasks are linked in chronological order (or you can define other priority), and within each task unit, there is a task object, which shows specific task to be done; the amount of resources needed is also marked in the task unit, corresponding to the specific task object. Generally, values for resources needed in tasks within completed task list are 0s, as completed tasks do not require further resources.

The executor would read in each task and query the system-wide resources availability. The system-wide resources database contains resource pieces, both from the system currently available and resource recycled from the task just completed. The database will answer the executor if there is enough resource for the task to be done, and will wait for executor to gather resources used by previous completed tasks, until there is enough resource so that the current task can be executed. The completed tasks are then returned to the completed tasks list. Note in the system-wide resources databse, resource pieces are also linked in certain order (e.g. chronological order), each not only shows value, but also location in the system.

## Example: Single Core Computer Task Scheduling

The example shows the model for task scheduling in a single core computer. The detail of this example can be mapped exactly from the explanation above, except for the executor and resources, which are replaced by CPU and memory.
