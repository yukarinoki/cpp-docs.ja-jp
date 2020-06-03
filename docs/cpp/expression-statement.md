---
title: 式ステートメント
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
ms.openlocfilehash: 2f12bbbafd9be50f851e36f472098431f9ac0d5d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189001"
---
# <a name="expression-statement"></a>式ステートメント

式ステートメントを使用すると、式が評価されます。 式ステートメントの結果として、制御が移動したり、イテレーションが発生したりすることはありません。

式ステートメントの構文は、次のように、単純です。

## <a name="syntax"></a>構文

```
[expression ] ;
```

## <a name="remarks"></a>解説

式ステートメント内の式はすべて評価され、次のステートメントが実行される前にすべての副作用が完了します。 最も一般的に使用される式ステートメントは、代入と関数呼び出しです。  式は省略可能であるため、セミコロンだけが、 [null](../cpp/null-statement.md)ステートメントと呼ばれる空の式ステートメントと見なされます。

## <a name="see-also"></a>参照

[C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)
