
# Context Api 

Context api example




## Installation





```bash
// create context 

import { createContext, useContext, useState } from "react";

const Data = createContext()


export const DataProvider = ({ children }) => {
    const [list, setList] = useState([])

    return (
        <Data.Provider value={{ list, setList }}>
            {children}
        </Data.Provider>

    )
}

export function useData() {
    return useContext(Data)
}

//use it 

<DataProvider>
    <div className="h-screen w-full flex">
        <div className=" w-[50%]">
            <Login />
         </div>
        <div className="bg-blue-400 w-[50%]">
            <Display />
        </div>
    </div>
</DataProvider>

```
    