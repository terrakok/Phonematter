#Phonematter

Phonematter provides a simple to use class for formatting and validating phone numbers in Android apps.

![alt tag](https://i.imgur.com/4nA9Eow.gif)

##Dependency

    repositories {
        maven { url "https://dl.bintray.com/terrakok/terramaven" }
    }
    
    dependencies {
        compile "com.terrakok.phonematter:phonematter:1.0@aar"
    }


##Usage

In its simplest form you do the following:

    PhoneFormat phoneFormat = new PhoneFormat(getContext());
    // Call any number of times
    String numberString = "..."; //the phone number to format
    String formattedString = phoneFormat.format(numberString);

You can also pass in a specific default country code if you don't want to rely on the Region Format setting. Pass in a valid ISO 3166-1 two-letter country code in lowercase:

    PhoneFormat phoneFormat = new PhoneFormat("uk", getContext());
    // Call any number of times
    String numberString = "..."; //the phone number to format
    String formattedString = phoneFormat.format(numberString);

You may also use the singleton interface if desired:

    PhoneFormat phoneFormat = PhoneFormat.getInstance(getContext());
    // Call any number of times
    String numberString = "..."; //the phone number to format
    String formattedString = phoneFormat.format(numberString);

To validate a phone number you can do the following:

    PhoneFormat phoneFormat = new PhoneFormat(getContext());
    // Call any number of times
    String numberString = "..."; //the phone number to validate
    boolean valid = phoneFormat.isPhoneNumberValid(numberString);
    
The phone number to validate can include formatting characters or not. The number will be valid if there are an appropriate set of digits.

PhoneFormat can also be used to lookup a country's calling code:

    PhoneFormat phoneFormat = PhoneFormat.getInstance(getContext());
    String callingCode = phoneFormat.callingCodeForCountryCode("AU"); // Australia - returns 61
    String defaultCallingCode = phoneFormat.defaultCallingCode(); // based on current Region Format (locale)

##About Me

Hi! I'm terrakok. I got this code from official Telegram android application (https://github.com/DrKLO/Telegram) and wrap it as small library.

##License
    Copyright (c) 2012, Rick Maddy
    All rights reserved.

    Redistribution and use in source and binary forms, with or without
    modification, are permitted provided that the following conditions are met:

    * Redistributions of source code must retain the above copyright notice, this
      list of conditions and the following disclaimer.

    * Redistributions in binary form must reproduce the above copyright notice,
      this list of conditions and the following disclaimer in the documentation
      and/or other materials provided with the distribution.

    THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
    ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
    WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
    DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
    FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
    DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS
    OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
    CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
    OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
    OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
