---
description: pragmaMicrosoft C/c + + での pointers_to_members ディレクティブの詳細については、こちらを参照してください。
title: pointers_to_members pragma
ms.date: 01/22/2021
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
helpviewer_keywords:
- class members, pointers to
- pragma, pointers_to_members
- members, pointers to
- pointers_to_members pragma
no-loc:
- pragma
ms.openlocfilehash: 7f2ca20b70d477e66a38d2a57e489d64c4179191
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713377"
---
# <a name="pointers_to_members-no-locpragma"></a>`pointers_to_members` pragma

**C++ 固有の仕様**

クラスメンバーへのポインターを、関連付けられているクラス定義の前に宣言できるかどうかを指定します。 ポインターのサイズ、およびポインターを解釈するために必要なコードを制御するために使用されます。

## <a name="syntax"></a>構文

> **`#pragma pointers_to_members(`***ポインター宣言*[ **`,`** *最も一般的な表現*]**`)`**

## <a name="remarks"></a>解説

**`pointers_to_members`** pragma [ `/vmb` また `/vmg` は](../build/reference/vmb-vmg-representation-method.md)コンパイラオプションや [継承キーワード](../cpp/inheritance-keywords.md)を使用する代わりに、ソースファイルにを配置できます。

*ポインター宣言* 引数は、関連付けられている関数定義の前または後に、メンバーへのポインターを宣言したかどうかを指定します。 *ポインター宣言* 引数は、次の2つの記号のいずれかになります。

| 引数 | コメント |
|--------------|--------------|
| **`full_generality`** | 安全な、場合によっては最適でないコードです。 **`full_generality`** メンバーへのポインターが、関連付けられているクラス定義の前に宣言されている場合は、を使用します。 この引数は、 *最も汎用表現* の引数で指定されたポインター表現を常に使用します。 と同じ **`/vmg`** です。 |
| **`best_case`** | メンバーへのすべてのポインターに対し、最適な表現を使用した安全で最適なコードを生成します。 クラスのメンバーへのポインターを宣言する前に、クラスを定義する必要があります。 既定値は **`best_case`** です。 |

*最も一般的* な引数は、変換単位のクラスのメンバーへのポインターを参照するためにコンパイラが安全に使用できる最小のポインター表現を指定します。 引数には、次のいずれかの値を指定できます。

| 引数 | コメント |
|--------------|--------------|
| **`single_inheritance`** | 最も一般的な表現は、単一継承、メンバー関数へのポインターです。 メンバーへのポインターが宣言されているクラス定義の継承モデルが多重継承モデルまたは仮想モデルの場合、エラーが発生します。 |
| **`multiple_inheritance`** | 最も一般的な表現は、多重継承、メンバー関数へのポインターです。 メンバーへのポインターが宣言されているクラス定義の継承モデルが仮想モデルの場合、エラーが発生します。 |
| **`virtual_inheritance`** | 最も一般的な表現は、仮想継承、メンバー関数へのポインターです。 エラーが発生することはありません。 **`virtual_inheritance`** は、が使用される場合の既定の引数です `#pragma pointers_to_members(full_generality)` 。 |

> [!CAUTION]
> を **`pointers_to_members`** pragma ソースコードファイルにのみ配置し、すべてのディレクティブの後にのみ含めるようにすることをお勧めし `#include` ます。 これにより、が pragma 他のファイルに影響を与えるリスクが軽減され、同じ変数、関数、またはクラス名に対して複数の定義が誤って指定されます。

## <a name="example"></a>例

```cpp
//   Specify single-inheritance only
#pragma pointers_to_members( full_generality, single_inheritance )
```

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
