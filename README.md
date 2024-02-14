import React , {useState} from 'react';
import axios from 'axios';


const Register = ()=>{
    const [user, setUser] = useState({
      username: "",
      email: "",
      password: "" 
    })
    const handlechange = e =>{
        const {name,value} =e.target
        
        setUser({
            ...user,
            [name]:value,
            
        })
    }
    const egister = () =>{
        const {username,email,password} = user
        if (username && email && password){
            axios.post("",user)
            .then.post(res=>console.log(res))
        }
        else{
            alert("invalid input")
        };
    }

    return(
        <>
         <div class="flex flex-col max-w-md px-4 py-8 bg-white rounded-lg shadow dark:bg-gray-800 sm:px-6 md:px-8 lg:px-10">
            <div class="self-center mb-2 text-xl font-light text-gray-800 sm:text-2xl dark:text-white">
                create a new account
            </div>
            <span class="justify-center text-sm text-center text-gray-500 flex-items-center dark:text-gray-400">Already have an account?
             <a href="login" target="_blank" class="text-sm text-blue-500 underline hover:text-blue-700">
            Sign in
             </a>
           </span>
           <div class="p-6 mt-8">
            <form action = "#">
                <div class="flex flex-col mb-2">
                    <div class="relative">
                    <label for="username" class="text-gray-600"> Name :</label>
                     <input type="text" id="username" class=" rounded-lg border-transparent flex-1 appearance-none border border-gray-300 w-full py-2 px-4 bg-white text-gray-700 placeholder-gray-400 shadow-sm text-base focus:outline-none focus:ring-2 focus:ring-purple-600 focus:border-transparent" name="name" value={user.name} onChange={handlechange} placeholder="name"/>
                    </div>
                    <div class="flex gap-4 mb-2">
                        <div class = "relative">
                        <label for="email" class="text-gray-600"> Email :</label>
                         <input type="text" id="email" class=" rounded-lg border-transparent flex-1 appearance-none border border-gray-300 w-full py-2 px-4 bg-white text-gray-700 placeholder-gray-400 shadow-sm text-base focus:outline-none focus:ring-2 focus:ring-purple-600 focus:border-transparent" name="email" value={user.email} onChange={handlechange} placeholder="email"/>
                        </div>
                        <div class="flex flex-col mb-2">
                            <div class="relative">
                            <label for="password" class="text-gray-600"> Password :</label>
                            <input type="password" id="password" class=" rounded-lg border-transparent flex-1 appearance-none border border-gray-300 w-full py-2 px-4 bg-white text-gray-700 placeholder-gray-400 shadow-sm text-base focus:outline-none focus:ring-2 focus:ring-purple-600 focus:border-transparent" name="password" value={user.password} onChange={handlechange}    placeholder="password"/>
                            </div>
                        </div>
                        <div class="flex w-full my-4">
                            <button type='submit' class="py-2 px-4  bg-purple-600 hover:bg-purple-700 focus:ring-purple-500 focus:ring-offset-purple-200 text-white w-full transition ease-in duration-200 text-center text-base font-semibold shadow-md focus:outline-none focus:ring-2 focus:ring-offset-2  rounded-lg " onClick={egister} >
                                    Register
                            </button>
                            </div>    

                    </div>

                </div>
            </form>

           </div>

         </div>
        </>
    )
}

export default Register;
