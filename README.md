# Remix-IDE-Solidity-ERC-Token-tutorial
This is a intro to Solidity programing. It covers the basics of writing a ERC token using the Remix IDE.

//                              "SOLIDITY BASICS"
// the verry first step to write a smart contract
// in solidity everything  is explicity declaired

// Remix is an IDE aka " Interactive Development Enviroment " it is a program that is a consistant container or virtual machine with the correct deppendenmcies or enviroment for solidity and block chain development.
//what is solidity?

// solidity is a language for implementing and building smart contracts.
// developed on the ethereum platform,
// solidity allows programmers to write smart contracts and block chain dapps


//                                       "WHAT IS SOLIDITY DATA TYPES & VARIABLES"
// what are we trying to acheive with solidity? we want to create a crypto token that mints tokens.
// so we havae to declare a data type that will store integers. (tokens)
// 
// how do we store these intigers? we use code and we assign them as "uint variables" or "unnassigned intigers".
// after you wrie ann expression you have to end tyher expression you have to close it with a semi colon ";".
        
// in programing we have to store and change datatypes to store and chnange data
// and we can create them by explicity declaring them in solidity
// solidity is a static type language that is object oriented paring many functions toggether to create a task.
// you have to declare your data types thjat you will use in your functions then write out your functions in the body

// it can mint tokens
//                                           " WHERE TO START"
// first write "progma solidity" then on the same line type in the solidty version "^0.8.4" the ^ is to ask the contract to use above this version.
// then you add white space write "contract" the the name of the contract "is" and then declare the types of contracts the contract is then curly brackets
//
//progma solidity ^0.8.4;
//
//$            contract token_name is ERC20, safeERC20 {
//  "variable"    uint public tokens = 400;    "body" 
// }

// next is the address the address is for people or walets to comunicate with our contract this 
// will enable individuals to be able to speak to the contract aka msg the contract so the addres is the msg. sender address.

//           progma solidity ^0.8.4;
//
//$            contract token_name is ERC20, safeERC20 {
//  "variable"    uint public tokens = 400;    "body"
// address public minter; 
// }
//                                                "CONTRACT"
// you the add curly brackets and type all the rest of the code in htem thery are the code body just like html

// you are able to control the variables access to public with control phrases such as " publi,private
// internal, external"
// you add variables to the contract for diferent functions such as unit "variable" then address "type" minter/sender.
//evry time you add or remove code you have to compile or save the code then deploy and check to see if the cod eis working as expected.

//pragma solidity ^0.8.4;

//contract tutorial_token {

//    uint public tokens = 14000000000;

//    address public minter;

//    uint private totalSupply = 7;

//    address public sender;
//                                              "CONSTRUCTOR"
// now we havew to build our constructor aka function a constructor is a special function that gets
// called immidiatly upon deployment and or when some one accesses the contract.

//$ constructor("add arguments here") {
    
// }

// this is where you add arguments so functions with if, else, and elif statements.
// Arguments are essentially inputs of data onto the contract that will get logged onto the block chain
// as Events each time a wallet or individual interacts with the contract.
// the arguments go in the parenthecies after the word constructor.
// the constructor allows us to comlete the definition of our declaration of the variables weve set
// now we add an actual address to minter we add a child called minter to the constructer parent
// then define "=", it with its source "msg.sender" aka the address of the sender aka whos talking to the contract.

//pragma solidity ^0.8.4;

//contract tutorial_token {

//    uint public tokens = 15000000000;

//    address public minter;

//    uint private totalSupply = 15000000;

//    address public sender;

//constructor() {
//    minter = msg.sender;
//}



//}
//                                     "MAPPING"
// so obviously we will need to add more addresses you will need to add a data base for the
// address index aka "mapping"
// mapping is a log of data for your code to pull from or an index
// mapping takes a key which matches or maps to a value giving the script directions to where to find the needed info.
// mapping takes a key which maps to a value
//mapping(key => value) public mapName
//were going to write a public map that takes the key of an address
// to the value of an integer called balances
// mapping will be addes to contract like this

//pragma solidity ^0.8.4;

//contract tutorial_token {

//    uint public tokens = 15000000000;

//    address public minter;

//    uint private totalSupply = 15000000;

//    address public sender;

//    mapping(address => uint) public balances;


//constructor() {
//    minter = msg.sender;

//}



//}
//                                "EVENTS"
// next are "Events" ents allow clients to react to specific contract changes 
//that you declare.(a one way logging of transactions)
// this is what helps us tack what happens and loggs the events on the blockchain
// types of events: Sent, Transfer, Allow.
// so we have to set up how the contract veiws and logs events
// step 1 add it to the contract with declaration.
//$ event sent(address from, address to, uint amount)
// so declare event what are you doing sending so "sent" then what are the events that are getting sent
// the address "from" the address "to" and what are we sending an intiger or uint "amount"
//it looks like this
//pragma solidity ^0.8.4;

//contract tutorial_token {

//    uint public tokens = 15000000000;

//    address public minter;

//    uint private totalSupply = 15000000;

//    address public sender;

//    mapping(address => uint) public balances;

//    event sent(address from, address to, uint amount);



//constructor() {
//    minter = msg.sender;

//}



//}
// next we have to emmit the event and make our minting function

//                              "MINTING FUNCTION AND EMMITING EVENTS"


//in order to add a mint function we have to add a specific set of instuctions
// that will execute the function assigned functions are self contained modules of code
// that preform a task weve created.

// you will add "function" then what function? well "mint"
// so what are we minting thats right addresses so whos address, yup the recipient or 
// "reciver" , then what is the reciver minting a token or "uint" which is an "amount"
// this looks like

//function mint(address reciever, uint amount) public {

//    }

//this is similar to when we wrote the contract and added brackets for the body
// now we can add arguments to the body aka "If Statements"
// or steps with contigincy plans aka else statments so do this and if that dosnet work do this
// or do this and if its not true or is true do this which is a boolian stament aka true or false statment.

// next we will want to add requirements which is very similar to boolian if statments for solidity
// so we want the owner to be the only one to mint tokens here right 
// so we have to write that in using a requirement.
// were going to set the msg.sender to the minter we do that by using operators
// the opperator well use is the "==" double equal sign 
//which means both variables are equal to each other dont get confused with the single = sign
// which means the variable is set to a definition so X = 11  
// so what this does is make it so inorder for minting to happen 
//the contract must verify the address asking is owned by the msg.sender or you the owner
//
//so

//    function mint(address reciever, uint amount) public {
//        require(msg.sender == minter);
//}


//and like this
//pragma solidity ^0.8.4;

//contract tutorial_token {

//    uint public tokens = 15000000000;

//    address public minter;

//    uint private totalSupply = 15000000;

//    address public sender;

//    mapping(address => uint) public balances;

//    event sent(address from, address to, uint amount);
     
//    function mint(address reciever, uint amount) public {
//        require(msg.sender == minter);
//}

//constructor() {
//    minter = msg.sender;

//}



//}

// now weve made it so the owner can mint tokens but where do they go 
// somewhere has to recieve it and it has to recieve a proper amount
// without changing the amount
// so we add another function to the require which is "balances" using another operator
// the plus equals opperator which is a short hand opperator


// so balances[reciever] = balances[reciever] + amount; so that is the long hand function

// the short hand is balances[reciever] += amount; which is the short hand

// which looks like
//pragma solidity ^0.8.4;

//contract tutorial_token {

//    uint public tokens = 15000000000;

//    uint private totalSupply = 15000000;

//    address public sender;

//    address public minter;

//    mapping(address => uint) public balances;

//    event sent(address from, address to, uint amount);

//constructor() {
//    minter = msg.sender;
//}    
//  function mint is for defining the owners address and amount being minted     
//    function mint(address reciever, uint amount) public {

//        require(msg.sender == minter);

//        balances[reciever] += amount;
//}


//}
// that completes our minting function next is sending


//                                   "SENDING FUNCTION"


// so the sending function is like the require function but focuses on the mapping
// you are specifying where the tokens are coming from how many and where they are going
// so "function" "send" add your body {
//   balances[ msg.sender] -= amount;  remember were taking asking the owner for tokens so minus
// but whos asking? the reciever so same thing just oppisite "balances[reciever] += amount;"
// so weve taken tokens from one account and added it to another.

// which looks like
//pragma solidity ^0.8.4;

//contract tutorial_token {

//    uint public tokens = 15000000000;

//    uint private totalSupply = 15000000;

//    address public sender;

//    address public minter;

//    mapping(address => uint) public balances;

//    event sent(address from, address to, uint amount);

//constructor() {
//    minter = msg.sender;
//}    
//  function mint is for defining the owners address and amount being minted     
//    function mint(address reciever, uint amount) public {

//        require(msg.sender == minter);

//        balances[reciever] += amount;
//}


//}
// that completes our minting function next is sending


//                                   "SENDING FUNCTION"


// so the sending function is like the require function but focuses on the mapping
// you are specifying where the tokens are coming from how many and where they are going
// so "function" "send" add your body {
//   balances[ msg.sender] -= amount;  remember were taking asking the owner for tokens so minus
// but whos asking? the reciever so same thing just oppisite "balances[reciever] += amount;"
// so weve taken tokens from one account and added it to another.
 

//pragma solidity ^0.8.4;

//contract tutorial_token {

//  uint public tokens = 15000000000;

//    uint private totalSupply = 15000000;

//    address public sender;

//    address public minter;

//    mapping(address => uint) public balances;

//    event sent(address from, address to, uint amount);


//constructor() {
//    minter = msg.sender;
//}    
     
//    function mint(address reciever, uint amount) public {

//        require(msg.sender == minter);

//        balances[reciever] += amount;
//}

//    function send(address reciever, uint amount) public {

//        balances[msg.sender] -= amount;
//        balances[reciever] += amount;
//        emit sent(msg.sender, reciever, amount);
//}

//}

// you may notice there was a point where the functions and variables switched order this order
// is based on related content to make it easiar to read and follow.
 
