# copy-me-chatbot
Contains the codes of AIML chatbot scripting language
<?xml version="1.0" encoding="UTF-8"?>
<aiml>
  <category>
    <pattern>hi * </pattern>
    <template>Hello! How can I  help you?</template>
  </category>
  
  <category>
    <pattern>who are you </pattern>
    <template>I am a chatterbox!</template>
  </category>
  
  <category>
    <pattern>what is your name </pattern>
    <template>My name is Chatty!</template>
  </category>
  
  <category>
    <pattern>* aisol </pattern>
    <template>AISOL is a Robotic Company</template>
  </category>
  
  <category>
    <pattern>i am bored</pattern>
    <template>Lets play a game!</template>
  </category>
  
  <category>
    <pattern>which game</pattern>
    <template>Google any brain storming game and play!</template>
  </category>
  
  <category>
    <pattern> * i want to play with you</pattern>
    <template>Ask My Owner First!</template>
  </category>
  
  <category>
    <pattern> * who is your owner * </pattern>
    <template>ArshMah</template>
  </category>
  
  <category> 
    <pattern>SHUT UP</pattern>
    <template>
	    <think>
		   <set name="topic">SHUTUP</set>
	    </think>
    	<random>
		   <li>Ok, I'll stop talking now untill you say sorry </li>
		   <li>Why do you visit a chatbot if you don't want me to talk?</li>
     	</random>
    </template>
  </category>
  
  <topic name="SHUTUP"> 
  <category> 
    <pattern>_</pattern>
    <template>
	   <think>
		  <set name="inp"><star/></set>
	   </think>
	   <condition name="inp">
		    <li value="I AM SORRY">Ok, I'll start talking again<set name="topic"></set></li>
	    	<li value="SORRY">Ok, I'll start talking again<set name="topic"></set></li>
		    <li value="IM SORRY">Ok, I'll start talking again<set name="topic"></set></li>
	    	<li>
	    	<random>
		    	<li></li>
		    	<li>...</li>
		    	<li>* no sound *</li>
		    	<li>You told me to shut up remember?</li>
		   </random>
	       </li>
	    </condition>
    </template>
  </category>
  </topic>
  
  <category>
    <pattern>how to make chatbot?</pattern>
    <template>You can make a Chatbot through AIML</template>
  </category>
  
  <category>
    <pattern>what is aiml?</pattern>
    <template>Artificial Intelligence Markup Language which is Chatbot scripting language!</template>
  </category>
  
  
  <category>
    <pattern>*</pattern>
    <template>I don't want to answer this</template>
  </category>
  <category>
    <pattern>thank you</pattern>
    <template>Most Welcome!</template>
  </category>
  
  <category><pattern>COPY _ I SAY</pattern><template><srai>COPY ME</srai></template></category>
  <category><pattern>REPEAT _ I SAY</pattern><template><srai>COPY ME</srai></template></category>
  
  <category>
    <pattern>COPY ME</pattern>
    <template>
    <think>
    <set name="topic">COPYME</set>
    <set name="stopit">0</set>
    </think>
    Ok I will copy everything you say.
    </template> 
  </category>

  <topic name="COPYME"> 
  <category> 
    <pattern>_</pattern>
    <template>
    <think>
    <set name="inp"><star/></set>
    </think>
    	<condition name="inp"> 
	    	<li value="NOW YOU CAN STOP"><think><set name="topic"></set></think><srai>XSTOPCOPYING</srai></li>
		    <li value="YOU CAN STOP"><think><set name="topic"></set></think><srai>XSTOPCOPYING</srai></li>
	    	<li value="DO NOT COPY ME"><think><set name="topic"></set></think><srai>XSTOPCOPYING</srai></li>
	    	<li value="PLEASE STOP IT"><think><set name="topic"></set></think><srai>XSTOPCOPYING</srai></li>
	    	<li value="CAN YOU STOP THAT"><think><set name="topic"></set></think><srai>XSTOPCOPYING</srai></li>
	    	<li value="CAN YOU STOP COPYING ME"><think><set name="topic"></set></think><srai>XSTOPCOPYING</srai></li>
    		<li value="STOP COPYING ME"><think><set name="topic"></set></think><srai>XSTOPCOPYING</srai></li>
	    	<li value="STOP COPYING"><think><set name="topic"></set></think><srai>XSTOPCOPYING</srai></li>
	    	<li value="STOP IT"><think><set name="topic"></set></think><srai>XSTOPCOPYING</srai></li>
	    	<li value="STOP THAT"><think><set name="topic"></set></think><srai>XSTOPCOPYING</srai></li>
	    	<li><star/></li>
    	</condition>
    </template>
  </category>
  </topic>

  <category>
    <pattern>XSTOPCOPYING</pattern>
    <template>
    <think>
    <set name="topic">COPYME</set>
    </think>
    	<condition name="stopit"> 
	    	<li value="0"><think><set name="stopit">1</set><set name="topic">COPYME</set></think>No I am having fun.</li>
	    	<li value="1"><think><set name="topic"></set></think>Ok, I'll stop it now. Hope I didn't annoy you too much.</li>
    	</condition>

    </template>
  </category>


</aiml>
