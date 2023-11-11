import React, { useState } from 'react';
import './Lamp.css';

const Lamp = () => {
 const [isOn, setIsOn] = useState(false);
 const [isOpen, setIsOpen] = useState(false);

 const toggleIsOn = () => {
    setIsOn(!isOn);
 };

 const toggleIsOpen = () => {
    setIsOpen(!isOpen);
 };

 return (
    <div className="lamp">
      <div className={`lamp-body ${isOpen ? 'open' : ''}`}>
        <div className={`lamp-bulb ${isOn ? 'on' : ''}`} onClick={toggleIsOn}></div>
      </div>
      <div className="lamp-base" onClick={toggleIsOpen}>
        {isOpen ? 'Close' : 'Open'}
      </div>
    </div>
 );
};

export default Lamp;

.lamp {
 width: 100px;
 height: 150px;
 display: flex;
 flex-direction: column;
 align-items: center;
 cursor: pointer;
}

.lamp-body {
 width: 100%;  
 height: 80px;
 background-color: #ccc;
 border-radius: 20px 20px 0 0;
 transition: transform 0.5s;
}

.lamp-body.open {
 transform: rotateX(180deg);
}

.lamp-bulb {
 width: 50px;
 height: 50px;
