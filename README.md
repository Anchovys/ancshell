# Anc Shell or AncShell
The special command interpreter. Can dynamic connect .DLL libraries

How to add DLL for load:



0. Run and Close AncShell (if file `adjuncts.txt` is not exsists),
1. Edit `adjuncts.txt` and add line `yourlib.dll` to end line file,
2. Save and close file `adjuncts.txt`,
3. Run AncShell.exe!

Your DLL library should have this  code for init by Anchshell:

`````csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Addons
{
    class __loadme
    {
        public bool Register( Type ShellType = null ) {
            
            //we return true if all success loaded
            return true;
            
            //or return false if all bad
            //return false;
        }
        
        public bool RunCommand( string cmd, string[] args ) {

            switch (cmd) {

                default: 
                
                    return false; //nothing to do 
                    
                break;
               
                case "somecmd":

                      /*
                      place here your code
                      */
                      
                       return true; //command successful execute
                       
                 break;

            }
        }
    }
}
