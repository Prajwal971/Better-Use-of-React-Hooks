# Better-Use-of-React-Hooks
Mistakes while using React-Hooks to be avoided.

1)
when using inputs feilds in the login or registration page or mostly when we useState()
Its better to use useRefs()

Ex:-
  const [email,setEmail] = useState("")
  
  function Onsubmit(e){
  clg(email)
  
  return(
    <form onSubmit={onSubmit}>
      <input
        value={email}
        onChange={e => SetEmail(e.target.value)}
      />
    </form>
  )
  
  OPTIMISED CODE
  
  Ex:-
  
   const emailRef = useRef("")
  
  function Onsubmit(e){
  clg({email : emailRef.current.value})
  
  return(
    <form onSubmit={onSubmit}>
      <input
        ref = {emailRef}
      />
    </form>
  )
  
**useState returns 2 properties or an array. One is the value or state and the other is the function to update the state. In contrast, useRef returns only one value which is the actual data stored. When the reference value is changed, it is updated without the need to refresh or re-render.**


2)
Use Function version when updating.
For Example when using counter function better to use a function.

Ex:-
  const [count,setCount] = useState(0)
  
  function addCounter(amount){
    setCount(count + amount)
  }
  
  return(
    <>
      <button onClick{() => addCounter(-1)> - </button>
      <span>{count}
      <button onClick{() => addCounter(1)> + </button>
    </>
  )
  
  OPTIMISED CODE
  
  Ex:-
    
  function addCounter(amount){
    setCount(currentCount => {
      return current Count + amount
    })
  }
  *UseState is always ASYNC i.e. we need to wait*
  *In that case use useEffect and set the dependency to the count means the useEffect runs always when and only when the count value chnages*
  
  
  
