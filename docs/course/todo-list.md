# ToDo List

![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/0.png)

ToDo List adalah aplikasi pencatatan tugas untuk produktivitas harian pengguna.
- Task Board [Lihat](https://spotty-cover-c24.notion.site/333aadc976b380abb118e5bcf8edce17?v=333aadc976b38152ac5c000cf66cd1b7)

##  Persiapan
- Design Systems [Download](#)
- Components Pagination [Download](#)
- Bootstrap v3.4 [Lihat](https://getbootstrap.com/docs/3.4/css/#overview)

## Langkah
- Buka GeneXus
- Tab *Tools* > Genexus Account... > Isi Info Login dan *Sign In*.
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/1.png)

- Import komponen persiapan yang sudah didownload. 
- Knowledge Manager > Import > Pilih file .XPZ lalu load
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/5.png)

- Buat sebuah Transaction <br>
Transaction ToDo
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/7.png)
Transaction ToDo Detail
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/8.png)

- Buat Structure Data Type (SDT)
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/6.png)
SDT Filter
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/9.png)
SDT Response
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/10.png)
SDT Todo
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/11.png)


- Buat Web Panel ToDo dan ToDO Detail
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/2.png)

- Buat tampilan seperti gambar <br>
Todo
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/3.png)
Todo Detail
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/4.png)

- Buat Procedures
![appendix here](https://raw.githubusercontent.com/PPU-Training/genexus/refs/heads/main/assets/images/course/todo-list/12.png)

- Kode procedure mengambil semua data (Server Side)
```gx
&SDT_Todos   = new()
&SDT_Response = new()

For Each
     Where todos_topic like '%' + &SDT_Filter.ByText + '%' 
        When not &SDT_Filter.ByText.IsEmpty()

     Where statusTodos_id = &SDT_Filter.ByStatusTodos_Id 
        When &SDT_Filter.ByStatusTodos_Id <> 0
	
    &item = new()
    &item.todos_id          = todos_id
    &item.todos_topic       = todos_topic
    &item.todos_description = todos_description
    &item.todos_dueDate     = todos_dueDate
    &item.statusTodos_title = statusTodos_title
    &item.todos_isActive    = todos_isActive

    &SDT_Todos.Add(&item)
EndFor

&SDT_Response.IsSuccess = True
&SDT_Response.Code      = "200"
&SDT_Response.Message   = "Success"
```

- Kode procedure mengambil data berdasarkan id (Server Side)
```gx
&SDT_Response = new()
&SDT_Todos    = new()

For Each
    Where todos_id = &todos_id 

    &SDT_Todos.todos_id          = todos_id
    &SDT_Todos.todos_topic       = todos_topic
    &SDT_Todos.todos_description = todos_description
    &SDT_Todos.todos_dueDate     = todos_dueDate
    &SDT_Todos.statusTodos_id    = statusTodos_id
    &SDT_Todos.todos_isActive    = todos_isActive
When None
    &SDT_Response.IsSuccess = False
    &SDT_Response.Code      = "404"
    &SDT_Response.Message   = "Data tidak ditemukan"
    Return
EndFor

&SDT_Response.IsSuccess = True
&SDT_Response.Code      = "200"
&SDT_Response.Message   = "Success"
```

- Kode procedure untuk membuat data baru (Server Side)
```gx
&SDT_Response = new()

New
    todos_id          = &SDT_Todos.todos_id
    todos_topic       = &SDT_Todos.todos_topic
    todos_description = &SDT_Todos.todos_description
    todos_dueDate     = &SDT_Todos.todos_dueDate
    statusTodos_id    = &SDT_Todos.statusTodos_id
    todos_isActive    = &SDT_Todos.todos_isActive
EndNew

If &Err = 0
    Commit
    &SDT_Response.IsSuccess = True
    &SDT_Response.Code      = "200"
    &SDT_Response.Message   = "Data berhasil disimpan"
Else
    Rollback
    &SDT_Response.IsSuccess = False
    &SDT_Response.Code      = "500"
    &SDT_Response.Message   = "Gagal menyimpan data"
EndIf
  ```
  
- Kode procedure untuk memperbaharui data (Server Side)
```gx
&SDT_Response = new()

For Each
    Where todos_id = &SDT_Todos.todos_id

    todos_topic       = &SDT_Todos.todos_topic
    todos_description = &SDT_Todos.todos_description
    todos_dueDate     = &SDT_Todos.todos_dueDate
    statusTodos_id    = &SDT_Todos.statusTodos_id
    todos_isActive    = &SDT_Todos.todos_isActive

When None
    &SDT_Response.IsSuccess = False
    &SDT_Response.Code      = "404"
    &SDT_Response.Message   = "Data tidak ditemukan"
    Return
EndFor

If &Err = 0
    Commit
    &SDT_Response.IsSuccess = True
    &SDT_Response.Code      = "200"
    &SDT_Response.Message   = "Data berhasil diupdate"
Else
    Rollback
    &SDT_Response.IsSuccess = False
    &SDT_Response.Code      = "500"
    &SDT_Response.Message   = "Gagal update data"
EndIf
```

- Kode procedure untuk menghapus data (Server Side)
```gx
&SDT_Response = new()

For Each
    Where todos_id = &todos_id

    Delete

When None
    &SDT_Response.IsSuccess = False
    &SDT_Response.Code      = "404"
    &SDT_Response.Message   = "Data tidak ditemukan"
    Return
EndFor

If &Err = 0
    Commit
    &SDT_Response.IsSuccess = True
    &SDT_Response.Code      = "200"
    &SDT_Response.Message   = "Data berhasil dihapus"
Else
    Rollback
    &SDT_Response.IsSuccess = False
    &SDT_Response.Code      = "500"
    &SDT_Response.Message   = "Gagal menghapus data"
EndIf
```

- Kode untuk perpindahan halaman (Client Side)
```gx
Event 'new todo'
	WP_TodoDetail(nullValue(&SDT_Todos.CurrentItem.todos_id))
EndEvent

Event 'edit'
	WP_TodoDetail(&SDT_Todos.CurrentItem.todos_id)
EndEvent
```

- Kode untuk Mengambil data dari procedure (Client Side)
```gx
	Proc_Todos(&SDT_Filter, &SDT_Todos, &SDT_Response)
```

- Kode filter data  (Client Side)
```gx
Event filtersearch.ControlValueChanging(&SDT_Filter)
  // Other Action
EndEvent

Event filterstatus.ControlValueChanged
  // Other Action
EndEvent
```

- Kode hapus filter  (Client Side)
```gx
Event 'reset'
	&SDT_Filter = NullValue(&SDT_Filter)
EndEvent
```

- Kode pagination (Client Side)
```gx
Event UC_Pagination.NextPage

	TableList.NextPage()
	Do 'NavigatePagination'
	Do 'GoToPageControlNavigate'

EndEvent

Event UC_Pagination.PreviousPage

	TableList.PreviousPage()
	Do 'NavigatePagination'
	Do 'GoToPageControlNavigate'

EndEvent

Event UC_Pagination.GoToPage

	&SelectedPage = &ToPageList.Item(UC_Pagination.SourceListCurrentIndex).ToPage
	TableList.GotoPage(&SelectedPage)
	Do 'NavigatePagination'
	Do 'GoToPageControl'

EndEvent

Sub 'PaginationFilter'

	&TotalRecords = TableList.RecordCount
	&PageCounts =  TableList.PageCount
	&LimitRow = 5
	&LimitPage = 5

	If &TotalRecords = 0
		PaginationWrapper.Class = "hidden"
	Else
		PaginationWrapper.Class = ""
		UC_Pagination.TotalRecords = &TotalRecords
		UC_Pagination.CurrentPage = TableList.CurrentPage
		UC_Pagination.CurrentRow = ((TableList.CurrentPage - 1) * &LimitRow) + 1


		If &TotalRecords < &LimitRow
			UC_Pagination.EndRow = &TotalRecords
		Else
			UC_Pagination.EndRow = &LimitRow
		EndIf

		UC_Pagination.TotalPage = &PageCounts

		If &PageCounts = 0
			UC_Pagination.NextClass = "disabled"
		EndIf

		if &PageCounts > 1
			&Count = 1
			&ToPageList = new()

			if &PageCounts >= 3
				&MaxPage = 3
			else
				&MaxPage = &PageCounts
			endif

			Do while &Count <= &MaxPage
				&ToPage = new()
				&ToPage.ToPage = &Count
				If &Count = UC_Pagination.CurrentPage
					&ToPage.ToPage_Class = "active"
				EndIf
				&ToPageList.Add(&ToPage)
				&Count += 1
			EndDo
		EndIf

		Do 'NavigatePagination'
		Do 'GoToPageControlNavigate'
	EndIf

EndSub

Sub 'NavigatePagination'

	UC_Pagination.CurrentPage = TableList.CurrentPage
	UC_Pagination.LimitRow = &LimitRow
	UC_Pagination.CurrentRow = ((TableList.CurrentPage - 1) * &LimitRow) + 1

	&EndRow = UC_Pagination.CurrentRow + &LimitRow - 1
	if &EndRow > &TotalRecords
		&EndRow = &TotalRecords
	endif
	UC_Pagination.EndRow = &EndRow

	uc_Pagination.PrevClass = ""
	uc_Pagination.NextClass = ""

	If TableList.CurrentPage = 1
		uc_Pagination.PrevClass = "disabled"
	EndIf

	If TableList.CurrentPage = TableList.PageCount
		uc_Pagination.NextClass = "disabled"
	EndIf

EndSub

Sub 'GoToPageControl'

	&Total = &PageCounts

	&SelectedPage = 0
	&Count = 1
	For &ToPage in &ToPageList
		If &Count = UC_Pagination.SourceListCurrentIndex
			&SelectedPage = &ToPage.ToPage
			exit
		EndIf
		&Count += 1
	Endfor


	&Current = &SelectedPage

	&ToPageList = new()

	if &Current <= 2
		&Start = 1
	else
		if &Current >= &Total - 1
			&Start = &Total - 2
		else
			&Start = &Current - 1
		endif
	endif

	if &Start < 1
		&Start = 1
	endif

	&Count = &Start
	&End = &Start + 2

	Do while &Count <= &End and &Count <= &Total
		&ToPage = new()
		&ToPage.ToPage = &Count
		If &Count = UC_Pagination.CurrentPage
			&ToPage.ToPage_Class = "active"
		EndIf
		&ToPageList.Add(&ToPage)
		&Count += 1
	EndDo

EndSub

Sub 'GoToPageControlNavigate'

	&Total = &PageCounts
	&Current = UC_Pagination.CurrentPage

	if &Current <= 0
		&Current = 1
	endif

	if &Current <= 2
		&Start = 1
	else
		if &Current >= &Total - 1
			&Start = &Total - 2
		else
			&Start = &Current - 1
		endif
	endif

	if &Start < 1
		&Start = 1
	endif

	&Count = &Start
	&End = &Start + 2

	&ToPageList = new()
	Do while &Count <= &End and &Count <= &Total
		&ToPage = new()
		&ToPage.ToPage = &Count
		If &Count = &Current
			&ToPage.ToPage_Class = "active"
		EndIf
		&ToPageList.Add(&ToPage)
		&Count += 1
	EndDo

EndSub
```
