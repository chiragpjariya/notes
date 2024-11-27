
# Redux Toolkit 

Redux Toolkit example









```bash
// create slices

import { createSlice, nanoid } from '@reduxjs/toolkit'


const initialState = {
    list: []
}

export const userSlice = createSlice({
    name: 'userData',
    initialState,
    reducers: {
        setData: (state, action) => {
            const data = {
                id: nanoid(),
                userName: action.payload.userName,
                userPassword: action.payload.userPassword
            }
            state.list.push(data)
        }
    }
   
    
})

export const { setData } = userSlice.actions
export default userSlice.reducer


//create store

import { configureStore } from "@reduxjs/toolkit";
import userReducer from './userSlice'


const store = configureStore({
    reducer: {
        user:userReducer
    }
})

export default store




//useSelector
const users = useSelector((state) => state.user.list);

//const variableName = useSelector((state)=> state.reducesName.data)


//useDisptach

const dispatch = useDispatch()
dispatch(setData({ userName: data.userName, userPassword: data.userPassword }));
```
    