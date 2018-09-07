---
title: C.1 表記 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a23b2631-8096-4bf3-ac23-ba4f4bd7a52a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d3ada700955c3acd2e96aa3e8a98c25c51393c1
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766153"
---
# <a name="c1-notation"></a>C.1 表記
文法規則は、非-ターミナルでの名前の後に別の行に交換用の代替手段を続けて、コロンです。

式の構文用語<sub>opt</sub>という用語が置換内で省略可能であることを示します。

構文の式*用語*<sub>optseq</sub>と等価*用語 seq*<sub>opt</sub>次の追加の規則で。

*用語 seq* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*用語*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*用語 seq* *用語*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*用語 seq* **、** *用語*