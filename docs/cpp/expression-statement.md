---
description: 詳細については、「式ステートメント」を参照してください。
title: 式ステートメント
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
ms.openlocfilehash: a208951c536883f2f08a6e856e9da48884255b1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186546"
---
# <a name="expression-statement"></a>式ステートメント

式ステートメントを使用すると、式が評価されます。 式ステートメントの結果として、制御が移動したり、イテレーションが発生したりすることはありません。

式ステートメントの構文は、次のように、単純です。

## <a name="syntax"></a>構文

```
[expression ] ;
```

## <a name="remarks"></a>解説

式ステートメント内の式はすべて評価され、次のステートメントが実行される前にすべての副作用が完了します。 最も一般的に使用される式ステートメントは、代入と関数呼び出しです。  式は省略可能であるため、セミコロンだけが、 [null](../cpp/null-statement.md) ステートメントと呼ばれる空の式ステートメントと見なされます。

## <a name="see-also"></a>関連項目

[C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)
