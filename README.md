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
  
**useState returns 2 properties or an array. One is the value or state and the other is the function to update the state. In contrast, useRef returns only one value which is the actual data stored. When the reference value is changed, it is updated without the need to refresh or re-render.
  **
