Agora React VideoUIKit

Instantly integrate Agora video calling or streaming into your web application using a React based VideoUIKit.


Installation

To a react application, add the following:

npm i agora-react-uikit


Usage

This UIKit contains a high level component called AgoraUIKit. You can check out code explanation here.

A simple sample app integrating Agora UI Kit:

import React, {useState} from 'react';

import AgoraUIKit from 'agora-react-uikit';


const App = () => {

  const [videoCall, setVideoCall] = useState(true);
  
  const rtcProps = {
  
    appId: '<Agora App ID>',
    
    channel: 'test', // your agora channel
    
    token: '<Your channel Token>' // use null or skip if using app in testing mode
    
  };
  
  const callbacks = {
  
    EndCall: () => setVideoCall(false),
    
  };
  
  return videoCall ? (
  
    <div style={{display: 'flex', width: '100vw', height: '100vh'}}>
    
      <AgoraUIKit rtcProps={rtcProps} callbacks={callbacks} />
      
    </div>
    
  ) : (
  
    <h3 onClick={() => setVideoCall(true)}>Start Call</h3>
    
  );
  
};


export default App;
