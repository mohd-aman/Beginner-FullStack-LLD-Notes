import { createStore } from "redux";


const initialState = 1000;
const store = createStore(reducer);


function reducer(state = initialState,action){
    if(action.type == 'Deposit') {
        return state+action.payload
    } else if(action.type == 'Withdraw') {
        return state-action.payload;
    } else if (action.type == 'Balance') {
        return state;
    } else {
        return state
    }
}

const depositAction = {type: 'Deposit', payload:100};
const withdrawAction = {type: 'Withdraw', payload:100};

// console.log(store.getState());
store.dispatch(depositAction);
// console.log(store.getState());
store.dispatch(withdrawAction);
// console.log(store.getState());

