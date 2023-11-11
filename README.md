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

