# basic way to use this package , you have to pass few things to Requirements

import { Requirements } from "react-component-lib-a"

function App() {
const [valid, setValid] = useState(false)
const [password, setPassword] = useState("")
const [username, setUsername] = useState("")

const passwordRequirements = [
{
text: "Must be at least 8 characters",
validator: (val) => val.length >= 8,
},
{
text: "Must contain at least one number",
validator: (val) => /\d/g.test(val),
},
{
text: "Must contain at least one lower-case letter",
validator: (val) => /[a-z]/g.test(val),
},
{
text: "Must contain at least one upper-case letter",
validator: (val) => /[A-Z]/g.test(val),
},
]

return (

<div className="App">
<header className="App-header">
<p>
Edit <code>src/App.js</code> and save to reload.
</p>

        <button label="My Design System Button" />
        <Requirements
          value={password}
          requirements={passwordRequirements}
          onValidChange={(isValid) => setValid(isValid)}
        />

        <input
          placeholder="Username"
          value={username}
          onChange={(e) => setUsername(e.target.value)}
        />
        <input
          placeholder="Password"
          type="password"
          value={password}
          onChange={(e) => setPassword(e.target.value)}
        />

        <button disabled={!valid || !username}>Sign Up</button>
      </header>
    </div>

)
}

export default App
