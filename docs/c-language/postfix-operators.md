---
description: '詳細情報: 後置演算子'
title: 後置演算子
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
ms.openlocfilehash: be8e7354d512174a4ab11ffcdcb82f9418baa894
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195867"
---
# <a name="postfix-operators"></a>後置演算子

後置演算子は、式の評価で優先順位が最高位 (最も強力なバインディング) になります。

## <a name="syntax"></a>構文

*postfix-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*primary-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **[**  *expression*  **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **(**  *argument-expression-list*<sub>opt</sub> **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **.**  *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **->**  *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **--**

この優先順位レベルの演算子は、配列の添字、関数呼び出し、構造体/共用体メンバー、および後置インクリメント/デクリメント演算子です。

## <a name="see-also"></a>関連項目

[C 演算子](../c-language/c-operators.md)
