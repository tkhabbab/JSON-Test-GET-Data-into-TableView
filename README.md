# JSON-Test-GET-Data-into-TableView
In this project i am doing get data into tableview and pass data into another view hear i am using JSONDECODER  for fatching data 


![screen shot 2018-09-25 at 10 47 57 am](https://user-images.githubusercontent.com/13781274/45994071-d3ce6d00-c0b3-11e8-818c-f9a6e5f047cd.png)


![screen shot 2018-09-25 at 10 48 16 am](https://user-images.githubusercontent.com/13781274/45994109-04160b80-c0b4-11e8-9f9d-dcf9264e831f.png)



 func getData(){
        
        let url = URL(string: "https://restcountries.eu/rest/v2/all")
        
        URLSession.shared.dataTask(with: url!) { (data, response, error) in
            do{if error == nil{
                self.arrdata = try JSONDecoder().decode([jsonstruct].self, from: data!)
                
                for mainarr in self.arrdata{
                    //print(mainarr.name,":",mainarr.capital,":",mainarr.alpha3Code)
                    DispatchQueue.main.async {
                        self.tableview.reloadData()
                    }
                    
                }
                }
                
            }catch{
                print("Error in get json data")
            }
            
            }.resume()
    }
