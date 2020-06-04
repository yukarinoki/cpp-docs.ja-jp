---
title: External Definitions (外部定義)
ms.date: 11/04/2016
helpviewer_keywords:
- external definitions
- external linkage, variable declarations
ms.assetid: 41e37bfc-b360-43b1-9972-28af2d365b20
ms.openlocfilehash: 7a05cf730940246c82963afbe27f6fa344951aeb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233675"
---
# <a name="external-definitions"></a>External Definitions (外部定義)

*translation-unit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*external-declaration* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*translation-unit* *external-declaration*

*external-declaration*: /\* 外部 (ファイル) スコープでのみ使用できる \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*function-definition*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*

*function-definition*: /\* この宣言子は関数宣言子 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

## <a name="see-also"></a>関連項目

[句の構造文法](../c-language/phrase-structure-grammar.md)
