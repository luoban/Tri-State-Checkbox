# Animated Tri State Checkbox
3 State Checkbox for **Android** in pure Material Style, with animation between the states.

[![Download](https://api.bintray.com/packages/kazakago/maven/tri-state-checkbox/images/download.svg)](https://bintray.com/kazakago/maven/tri-state-checkbox/_latestVersion)
[![Build Status](https://app.bitrise.io/app/440c28e73a153e24/status.svg?token=tBmmmhVrhSUYX88cbFRe3w&branch=master)](https://app.bitrise.io/app/440c28e73a153e24)
[![license](https://img.shields.io/github/license/kazakago/tri-state-checkbox.svg)](LICENSE.md)

<img src="./art/checkbox.gif" width="360" height="740" />

# Usage

In your layout:

    <it.sephiroth.android.library.checkbox3state.CheckBox3
        android:id="@+id/checkBox1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:checked="true"
        app:sephiroth_checkbox3_indeterminate="true"
        android:text="Select All"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView1"
        app:sephiroth_checkbox3_checkableCycle="@array/sephiroth_checkbox3_cycleIndeterminate"
             />


In Kotlin:

    // set both the checked and indeterminate state
    checkbox.setChecked(true, true)

    // set the indeterminate state only
    checkBox.isIndeterminate = false


## Cycles:

Change the cycle used to determine the next state of the checkbox when the user click the component, or when the **toggle()** method is called.<br />
The value passed is an array of 4 integer elements, representing the state of the checkbox.<br />
The value of each element can be 0 or 1, with 0 to disable the state and 1 to enable the state.<br />
The states are (in order):

- Checked
- Indeterminate (checked)
- Unchecked
- Indeterminate (unchecked)
     
So if a cycle like this one is used:

    int[] cycle = new int[]{1,0,1,0}

the checkbox will only cycle between checked and unchecked state.<br />

The method throws an exception if the array is not valid.<br />
A valid array must match the following rules:
- If not null, must have 4 elements
- At least 2 elements must be equal to 1

In Kotlin:
    
    checkBox1.setCycle(intArrayOf(1, 0, 1, 0))

In xml layout:

    app:sephiroth_checkbox3_checkableCycle="@array/sephiroth_checkbox3_cycleCheckedUncheckedOnly"

# Installation

## Gradle

    implementation 'com.kazakago.tri-state-checkbox:tri-state-checkbox:{version}'

Get the latest version  on [![Download](https://api.bintray.com/packages/kazakago/maven/tri-state-checkbox/images/download.svg)](https://bintray.com/kazakago/maven/tri-state-checkbox/_latestVersion)

# License

MIT License

Copyright (c) 2019 Alessandro Crugnola

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
