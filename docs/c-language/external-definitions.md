---
description: '詳細情報: External Definitions (外部定義)'
title: External Definitions (外部定義)
ms.date: 11/04/2016
helpviewer_keywords:
- external definitions
- external linkage, variable declarations
ms.assetid: 41e37bfc-b360-43b1-9972-28af2d365b20
ms.openlocfilehash: 6bdc9299f68b0c05f58c7f3620f9de5ce76a98e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196296"
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
