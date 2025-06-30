# Office 365 PowerShell Command Generator

This project provides a simple web interface to generate PowerShell commands for managing Office 365 calendar delegations.

## Overview

The core of this project is the `index.html` file. When opened in a web browser, it presents a form where users can input:

*   **Delegate UPN:** The User Principal Name (UPN) of the user who will receive the calendar permissions.
*   **Access Level:** The desired permission level (e.g., Reviewer, Editor, Owner).
*   **Owner UPNs:** A list of UPNs for the calendar owners. Multiple UPNs can be entered, separated by commas, newlines, or semicolons.

Based on these inputs, the page generates a PowerShell script that can be run to apply the specified calendar permissions in an Office 365 environment.

## Usage

1.  Clone or download this repository.
2.  Open the `index.html` file in your preferred web browser.
3.  Fill in the required fields in the form:
    *   Delegate UPN
    *   Access Level
    *   Owner UPN(s)
4.  Optionally, check the box to include `-ErrorAction SilentlyContinue` in the generated commands. This prevents errors if a permission already exists.
5.  Click the "צור פקודות PowerShell" (Generate PowerShell Commands) button.
6.  The generated PowerShell script will appear in the text area below the button.
7.  Click the "העתק ללוח" (Copy to Clipboard) button to copy the script.
8.  Paste and run the script in a PowerShell session connected to your Exchange Online environment (using `Connect-ExchangeOnline`).

## Technical Details

*   The user interface is built with HTML and styled using **Tailwind CSS** (via CDN).
*   Client-side JavaScript is used to:
    *   Read the input values from the form.
    *   Construct the PowerShell commands.
    *   Display the generated script.
    *   Provide a "copy to clipboard" functionality.

## Purpose

This tool aims to simplify the process of granting calendar permissions for multiple users in Office 365 by automating the generation of the necessary PowerShell commands. This can be particularly useful for IT administrators who frequently manage such permissions.

## CNAME File

The `CNAME` file in this repository is likely used for custom domain configuration with GitHub Pages, pointing `delegation-helper.ravkavonline.co.il` to the GitHub Pages site where this project is hosted.
