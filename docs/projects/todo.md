
UI
- MasterLayout -> Web Master Panel
- WP_Todo -> Web Panel
- WP_TodoDetail -> Web Panel
- ToDoList -> Design Systems

Schema
Schema of Todos
   {
        "todos_id": 1,
        "todos_topic": "Belajar Genexus",
        "todos_description": "Belajar Genexus Di Perkasa Pilar Utama",
        "todos_dueDate": "2026-04-02",
        "statusTodos_id": 1,
        "todos_isActive": true
    }
Schema of StatusTodos
   {
        "statusTodos_id": 1,
        "statusTodos_tile": "Done",
        "statusTodos_isActive": true
    }

Transaction
- Trx_Todo > Schema of Todo
- Trx_StatusTodo > Schema of StatusTodo

SDT
- SDT_Response
   {
        "IsSuccess": true,
        "Code": "",
        "Message": ""
    }
- SDT_Filter
     {
        "ByText": "",
        "ByStatusId": 1,
    }
- SDT_Todos
   {
        "todo_id": 1,
        "todo_topic": "Belajar Genexus",
        "todo_description": "Belajar Genexus Di Perkasa Pilar Utama",
        "todo_dueDate": "2026-04-02",
        "statusTodo_id": 1,
        "todo_isActive": true
    }

Procedure
- Proc_Todos
&Todos = New()

For Each Trx_Todos
	   Where (
        &Filter.FilterByText.IsEmpty() or 
        Trx_Todos_Topic like '%' + &Filter.FilterByText + '%' or
        Trx_Todos_Description like '%' + &Filter.FilterByText + '%')
    Where ( &Filter.FilterByStatus = 0 or TodoStatus_ID = &Filter.FilterByStatus)
    
	&TodoItem = New()
	
	&TodoItem.Todo_ID = Trx_Todos_ID
	&TodoItem.Todo_Topic = Trx_Todos_Topic
	&TodoItem.Todo_Description = Trx_Todos_Description
	&TodoItem.Todo_DueDate = Trx_Todos_DueDate
	&TodoItem.Todo_Status = TodoStatus_Title
	&TodoItem.Todo_IsActive = Trx_Todos_IsActive
	
	&Todos.Add(&TodoItem)
EndFor



&Response.IsSuccess = true
&Response.Code = '200'

If &Todos.Count = 0
    &Response.Message = 'No data found'
Else
    &Response.Message = 'Data retrieved successfully'
EndIf
