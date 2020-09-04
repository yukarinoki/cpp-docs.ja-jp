---
title: C ステートメントの概要
description: Microsoft C 実装におけるステートメント文法の概要です。
ms.date: 08/24/2020
ms.assetid: ce45d2fe-ec0e-459f-afb1-80ab6a7f0239
ms.openlocfilehash: 448aa7ccb8c78e20ef09f47f4a3c77f447c76f60
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898397"
---
# <a name="summary-of-c-statements"></a>C ステートメントの概要

*`statement`*:<br/>
&emsp;*`labeled-statement`*<br/>
&emsp;*`compound-statement`*<br/>
&emsp;*`expression-statement`*<br/>
&emsp;*`selection-statement`*<br/>
&emsp;*`iteration-statement`*<br/>
&emsp;*`jump-statement`*<br/>
&emsp; *`try-except-statement`*  /\* Microsoft 固有の仕様 \*/<br/>
&emsp; *`try-finally-statement`*  /\* Microsoft 固有の仕様 \*/

*`jump-statement`*:<br/>
&emsp;**`goto`** *`identifier`* **`;`**<br/>
&emsp;**`continue ;`**<br/>
&emsp;**`break ;`**<br/>
&emsp; **`return`** *`expression`* <sub>opt</sub> **`;`**<br/>
&emsp; **`__leave ;`**  /\* Microsoft 固有の仕様<sup>1</sup> \*/

*`compound-statement`*:<br/>
&emsp; **`{`** *`declaration-list`* <sub>opt</sub> *`statement-list`* <sub>opt</sub> **`}`**

*`declaration-list`*:<br/>
&emsp;*`declaration`*<br/>
&emsp;*`declaration-list`* *`declaration`*

*`statement-list`*:<br/>
&emsp;*`statement`*<br/>
&emsp;*`statement-list`* *`statement`*

*`expression-statement`*:<br/>
&emsp; *`expression`* <sub>opt</sub> **`;`**

*`iteration-statement`*:<br/>
&emsp;**`while (`** *`expression`* **`)`** *`statement`*<br/>
&emsp;**`do`** *`statement`* **`while (`** *`expression`* **`) ;`**<br/>
&emsp; **`for (`** *`expression`* <sub>opt</sub> **`;`** *`expression`* <sub>opt</sub> **`;`** *`expression`* <sub>opt</sub> **`)`** *`statement`*

*`selection-statement`*:<br/>
&emsp;**`if (`** *`expression`* **`)`** *`statement`*<br/>
&emsp;**`if (`** *`expression`* **`)`** *`statement`* **`else`** *`statement`*<br/>
&emsp;**`switch (`** *`expression`* **`)`** *`statement`*

*`labeled-statement`*:<br/>
&emsp;*`identifier`* **`:`** *`statement`*<br/>
&emsp;**`case`** *`constant-expression`* **`:`** *`statement`*<br/>
&emsp;**`default :`** *`statement`*

*`try-except-statement`* : /\* Microsoft 固有の仕様 \*/<br/>
&emsp;**`__try`** *`compound-statement`* **`__except (`** *`expression`* **`)`** *`compound-statement`*

*`try-finally-statement`* : /\* Microsoft 固有の仕様 \*/<br/>
&emsp;**`__try`** *`compound-statement`* **`__finally`** *`compound-statement`*

1 **`__leave`** キーワードは、 *`try-except-statement`* または *`try-finally-statement`* の **`__try`** ブロック内でのみ有効です。

## <a name="see-also"></a>関連項目

[語句構造の文法](../c-language/phrase-structure-grammar.md)
