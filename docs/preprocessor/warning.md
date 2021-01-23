---
title: 要する pragma
description: pragmaMicrosoft C/c + + の警告についての詳細情報
ms.date: 01/22/2021
f1_keywords:
- warning_CPP
- vc-pragma.warning
helpviewer_keywords:
- pragma, warning
- push pragma warning
- pop warning pragma
- warning pragma
no-loc:
- pragma
ms.openlocfilehash: 97d48acc3c0e4651d3b05c0a6405d5c9c2031cf6
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712844"
---
# <a name="warning-no-locpragma"></a>`warning` pragma

コンパイラの警告メッセージの動作の選択的な変更を有効にします。

## <a name="syntax"></a>構文

> **`#pragma warning(`**\
> &nbsp;&nbsp;&nbsp;&nbsp;*`warning-specifier`* **`:`** *`warning-number-list`*\
> &nbsp;&nbsp;&nbsp;&nbsp;[**`;`** *`warning-specifier`* **`:`** *`warning-number-list`* ... ] **`)`**\
> **`#pragma warning( push`** [ **`,`** *n* ] **`)`**\
> **`#pragma warning( pop )`**

## <a name="remarks"></a>解説

次の警告指定子パラメーターを使用できます。

| 警告指定子 | 意味 |
|--|--|
| `1`, `2`, `3`, `4` | 指定した警告に特定のレベルを適用します。 は、既定ではオフになっている、指定された警告もオンにします。 |
| `default` | 警告の動作を既定値にリセットします。 は、既定ではオフになっている、指定された警告もオンにします。 警告は、既定の文書化されたレベルで生成されます。<br /><br /> 詳細については、「 [既定でオフになっているコンパイラ警告](../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。 |
| `disable` | 指定された警告メッセージを発行しません。 |
| `error` | 指定した警告をエラーとして報告します。 |
| `once` | 指定したメッセージを 1 回だけ表示します。 |
| `suppress` | の現在の状態を pragma スタックにプッシュし、次の行に対して指定された警告を無効にして、 pragma 状態がリセットされるように警告スタックをポップします。 |

次のコードステートメントは、 *`warning-number-list`* パラメーターに複数の警告番号を含めることができ、複数の *`warning-specifier`* パラメーターを同じディレクティブで指定できることを示してい pragma ます。

```cpp
#pragma warning( disable : 4507 34; once : 4385; error : 164 )
```

このディレクティブは、機能的には次のコードと同等です。

```cpp
// Disable warning messages 4507 and 4034.
#pragma warning( disable : 4507 34 )

// Issue warning C4385 only once.
#pragma warning( once : 4385 )

// Report warning C4164 as an error.
#pragma warning( error : 164 )
```

コンパイラは、0 と 999 の間の任意の警告番号に 4000 を追加します。

4700-4999 の範囲の警告番号は、コード生成に関連付けられています。 これらの警告の場合、コンパイラが関数定義に到達したときに有効な警告の状態は、関数の残りの部分に対して有効なままです。 関数のを使用して、 **`warning`** pragma 4699 より大きい警告番号の状態を変更することは、関数の終了後にのみ有効になります。 次の例は、 **`warning`** コード生成の警告メッセージを無効にしてから復元するためのの正しい配置を示して pragma います。

```cpp
// pragma_warning.cpp
// compile with: /W1
#pragma warning(disable:4700)
void Test() {
   int x;
   int y = x;   // no C4700 here
   #pragma warning(default:4700)   // C4700 enabled after Test ends
}

int main() {
   int x;
   int y = x;   // C4700
}
```

関数本体全体で、の最後の設定が **`warning`** pragma 関数全体に対して有効になることに注意してください。

## <a name="push-and-pop"></a>プッシュとポップ

では、 **`warning`** pragma 次の構文もサポートされています。省略可能な *n* パラメーターは、警告レベル (1 ~ 4) を表します。

`#pragma warning( push [ , n ] )`

`#pragma warning( pop )`

は、 pragma `warning( push )` すべての警告について現在の警告状態を格納します。 は、 pragma `warning( push, n )` すべての警告の現在の状態を格納し、グローバル警告レベルを *n* に設定します。

は、 pragma `warning( pop )` スタックにプッシュされた最後の警告状態をポップします。 との間で警告状態に加えた変更 `push` `pop` は元に戻されます。 次の例について考えます。

```cpp
#pragma warning( push )
#pragma warning( disable : 4705 )
#pragma warning( disable : 4706 )
#pragma warning( disable : 4707 )
// Some code
#pragma warning( pop )
```

このコードの最後で、は、 `pop` すべての警告 (4705、4706、および4707を含む) の状態を、コードの開始時点の状態に復元します。

ヘッダーファイルを記述するときに、およびを使用し `push` `pop` て、ユーザーが行った警告状態の変更によって、ヘッダーが正しくコンパイルされないようにすることができます。 `push`ヘッダーの先頭と末尾にを使用し `pop` ます。 たとえば、警告レベル4では正常にコンパイルされないヘッダーがある場合があります。 次のコードでは、警告レベルを3に変更し、ヘッダーの最後に元の警告レベルを復元します。

```cpp
#pragma warning( push, 3 )
// Declarations/definitions
#pragma warning( pop )
```

警告を抑制するのに役立つコンパイラオプションの詳細については、「」および「」を参照してください [`/FI`](../build/reference/fi-name-forced-include-file.md) [`/w`](../build/reference/compiler-option-warning-level.md) 。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
