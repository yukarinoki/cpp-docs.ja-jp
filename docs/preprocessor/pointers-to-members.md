---
title: pointers_to_members プラグマ
ms.date: 08/29/2019
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
helpviewer_keywords:
- class members, pointers to
- pragmas, pointers_to_members
- members, pointers to
- pointers_to_members pragma
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
ms.openlocfilehash: fb5b277252b6c1422a87c5f2a2e2b7230ec49632
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219065"
---
# <a name="pointers_to_members-pragma"></a>pointers_to_members プラグマ

**C++のみ**

クラスメンバーへのポインターを、関連付けられているクラス定義の前に宣言できるかどうかを指定します。 ポインターのサイズ、およびポインターを解釈するために必要なコードを制御するために使用されます。

## <a name="syntax"></a>構文

> **#pragma pointers_to_members (** *ポインター宣言*[ **、** *最も一般的な表現*])

## <a name="remarks"></a>Remarks

**Pointers_to_members**プラグマは、 [/vmb または/vmg](../build/reference/vmb-vmg-representation-method.md)コンパイラオプションや[継承キーワード](../cpp/inheritance-keywords.md)を使用する代わりに、ソースファイルに配置できます。

*ポインター宣言*引数は、関連付けられている関数定義の前または後に、メンバーへのポインターを宣言したかどうかを指定します。 *ポインター宣言*引数は、次の2つの記号のいずれかになります。

| 引数 | コメント |
|--------------|--------------|
| **full_generality** | 安全な、場合によっては最適でないコードです。 メンバーへのポインターが、関連付けられているクラス定義の前に宣言されている場合は、 **full_generality**を使用します。 この引数は、*最も汎用表現*の引数で指定されたポインター表現を常に使用します。 これは /vmg と同じです。 |
| **best_case** | メンバーへのすべてのポインターに対し、最適な表現を使用した安全で最適なコードを生成します。 クラスのメンバーへのポインターを宣言する前に、クラスを定義する必要があります。 既定値は**best_case**です。 |

*最も一般的*な引数は、変換単位のクラスのメンバーへのポインターを参照するためにコンパイラが安全に使用できる最小のポインター表現を指定します。 引数には、次のいずれかの値を指定できます。

| 引数 | コメント |
|--------------|--------------|
| **single_inheritance** | 最も一般的な表現は、単一継承、メンバー関数へのポインターです。 メンバーへのポインターが宣言されているクラス定義の継承モデルが多重継承モデルまたは仮想モデルの場合、エラーが発生します。 |
| **multiple_inheritance** | 最も一般的な表現は、多重継承、メンバー関数へのポインターです。 メンバーへのポインターが宣言されているクラス定義の継承モデルが仮想モデルの場合、エラーが発生します。 |
| **virtual_inheritance** | 最も一般的な表現は、仮想継承、メンバー関数へのポインターです。 エラーが発生することはありません。 **virtual_inheritance**は、が使用さ`#pragma pointers_to_members(full_generality)`れている場合の既定の引数です。 |

> [!CAUTION]
> **Pointers_to_members**プラグマは、適用するソースコードファイルと、 `#include`ディレクティブの後にのみ配置することをお勧めします。 これにより、プラグマが他のファイルに影響を与えるリスクが減少すると共に、同じ変数、関数、またはクラス名に誤って複数の定義を指定するリスクが減少します。

## <a name="example"></a>例

```cpp
//   Specify single-inheritance only
#pragma pointers_to_members( full_generality, single_inheritance )
```

**特定C++の終了**

## <a name="see-also"></a>関連項目

[プラグマディレクティブと __ プラグマキーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
