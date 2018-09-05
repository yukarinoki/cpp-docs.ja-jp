---
title: 規則 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- preprocessor, conventions
ms.assetid: 469ce448-dc6c-4d0e-ba2b-e2e7a10155e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccb595911ef3032b652faedf1195f95b468d30e9
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761957"
---
# <a name="conventions"></a>規約
構文規則では、構文のコンポーネントごとに異なるフォント属性を使用します。 シンボルとフォントは次のとおりです。

|属性|説明|
|---------------|-----------------|
|*nonterminal*|斜体は、非終端要素を示します。|
|#include|太字で示される終端要素は、示されたとおりに入力する必要があるリテラル予約語およびシンボルです。 このコンテキストの文字は、常に大文字と小文字が区別されます。|
|opt|非終端要素が続く<sub>opt</sub>は常に省略可能です。|
|既定のタイプフェイス|このタイプフェイスで記述されているか、示されているセット内の文字は、ステートメント内で終端要素として使用できます。|

非終端要素に続くコロン (**:**) は、定義の説明を示します。 代替定義は別の行に示されます。

## <a name="see-also"></a>関連項目

[文法の概要 (C/C++)](../preprocessor/grammar-summary-c-cpp.md)