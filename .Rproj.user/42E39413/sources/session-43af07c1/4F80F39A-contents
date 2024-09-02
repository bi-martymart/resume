my_details <- function(){
  
  dependencies <- c('readxl','dplyr')
  
  for(package in dependencies) {
    if(!requireNamespace(package)) install.packages(package)
    
    library(package, character.only = TRUE)
  }
  
  tryCatch(
    expr = {
      
    sheets_names <- excel_sheets("data/details.xlsx")
    
    sheet_list <- lapply(sheets_names,
                         function(sheet_name) read_excel("data/details.xlsx", sheet = sheet_name))
    
    names(sheet_list) <- sheets_names
      
    },
    error = function(e) print("An error occurred")
  )
  
  return(sheet_list)
}
