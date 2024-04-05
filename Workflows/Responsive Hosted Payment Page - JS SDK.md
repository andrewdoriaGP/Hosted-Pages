# Responsive Hosted Payment Page - JS SDK

PayFabric provides a JavaScript library to support both Alternative Payment Methods as well as interaction with our new responsive Hosted Payment Page. This JavaScript Library hosted by PayFabric will be responsible for configuring and presenting a payment popup or element that supports our hosted payment page as well as any alternative payment methods PayFabric supports today or into the future.

PayFabric released a new version of our JavaScript SDK during our Nov. release of PayFabric. This new version supports a new responsive wallet page. Looking for previous versions of our JavaScript SDK? Click V1 and V2.

## Overview

** Overview Intro

** Generate JWT Token

** Payment Page Link

** Available options

** Retrieve Response


## Generate JWT Token

** Overview Intro

** Generate Security Token

** Generate New Transaction

** Payment Page Link (Mobile Responsive)

** Payment Page Link (include terminal entry and sig)

** Retrieve Response


## Payment Pages

Please check the detailed instructions for [Alternative Payment Methods](https://github.com/PayFabric/Portal/blob/master/PayFabric/Sections/APM.md)

<b>Note:</b> 
1. Alternative payment methods are not available for the transaction enable surcharge or enabled tip.
2. Additionally, if you are using an iFrame approach for Google Pay, then you must add `allow="payment"` attribute to your iframe.

## Available Options

3D Secure 2.0 is a protocol that was developed in compliance with the PSD2 (Payment Service Directive 2.0) mandate to make online payments more secure through advanced cardholder verification.

Only 3D Secure 2.0 is supported on Mobile Hosted Payment Page with the gateway as EVO and its the processor is EVO eService.

## Retrieve Response

The Payment Terminals Signature page is used to retrieve the PNG version of the signature for the transaction created from Payment Terminals.

Before embedding the signature page, please ensure the following:

1. Generate a [Security Token](/Sections/Security%20Token.md).  Assume the token value is @TOKEN.
2. Generate a new transaction with Payment Terminals, see our [Payment Terminals](../../../../PayFabric/Portal/blob/master/PayFabric/Sections/Payment%20Terminals.md) for how.  Assume the transaction key is @TRXKEY.

Open the signature page with this URL:

https://sandbox.payfabric.com/Payment/Web/Transaction/GetSignature?key={@TRXKEY}&token={@TOKEN}

