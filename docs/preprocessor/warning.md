---
title: warning プラグマ
ms.date: 08/29/2019
f1_keywords:
- warning_CPP
- vc-pragma.warning
helpviewer_keywords:
- pragmas, warning
- push pragma warning
- pop warning pragma
- warning pragma
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
ms.openlocfilehash: 9a79f0c4a9eed6b62e42f056f9d1994b44b57297
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216475"
---
# <a name="warning-pragma"></a>warning プラグマ

コンパイラの警告メッセージの動作の選択的な変更を有効にします。

## <a name="syntax"></a>構文

> **#pragma の警告 (**\
> &nbsp;&nbsp;&nbsp;&nbsp;*警告-指定子***:***警告-番号リスト*\
> &nbsp;&nbsp;&nbsp;&nbsp;[**;***警告-指定子***:***警告-番号一覧*...]**)**\
> **#pragma の警告 (プッシュ**[ **,** *n* ] **)**\
> **#pragma 警告 (pop)**

## <a name="remarks"></a>Remarks

次の警告指定子パラメーターを使用できます。

|警告指定子|説明|
|------------------------|-------------|
|*1、2、3、4*|指定された警告に特定のレベルを適用します。 は、既定ではオフになっている、指定された警告もオンにします。|
|*default*|警告の動作を既定値にリセットします。 は、既定ではオフになっている、指定された警告もオンにします。 警告は、既定の文書化されたレベルで生成されます。<br /><br /> 詳細については、「[既定でオフになっているコンパイラ警告](../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。|
|*disable*|指定された警告メッセージを発行しません。|
|*error*|指定した警告をエラーとして報告します。|
|*once*|指定したメッセージを 1 回だけ表示します。|
|*振ら*|プラグマの現在の状態をスタックにプッシュし、次の行に対して指定された警告を無効にします。次に、プラグマの状態がリセットされるように警告スタックをポップします。|

次のコード ステートメントは、`warning-number-list` パラメーターが複数の警告の数を含むことができること、および複数の `warning-specifier` パラメーターが同じプラグマ ディレクティブで指定できることを示しています。

```cpp
#pragma warning( disable : 4507 34; once : 4385; error : 164 )
```

このディレクティブは、機能的には次のコードと同等です。

```cpp
// Disable warning messages 4507 and 4034.
#pragma warning( disable : 4507 34 )

// Issue warning 4385 only once.
#pragma warning( once : 4385 )

// Report warning 4164 as an error.
#pragma warning( error : 164 )
```

コンパイラは、0 と 999 の間の任意の警告番号に 4000 を追加します。

コードの生成に関連する 4700 ～ 4999 の警告番号の場合、コンパイラで関数の左中かっこが検出された場合の有効な警告の状態は、他の関数に対しても有効になります。 関数の**warning**プラグマを使用して、4699より大きい警告番号の状態を変更することは、関数の終了後にのみ有効になります。 次の例では、コード生成の警告メッセージを無効にして復元するために、**警告**プラグマの正しい配置を示しています。

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

関数本体全体で、**警告**プラグマの最後の設定が関数全体に対して有効になることに注意してください。

## <a name="push-and-pop"></a>プッシュおよびポップ

**Warning**プラグマでは、次の構文もサポートされています。 *n*は警告レベル (1 ~ 4) を表します。

`#pragma warning( push [ , n ] )`

`#pragma warning( pop )`

プラグマ`warning( push )`は、警告ごとに現在の警告状態を格納します。 プラグマ`warning( push, n )`は、すべての警告の現在の状態を格納し、グローバル警告レベルを*n*に設定します。

プラグマ`warning( pop )`は、スタックにプッシュされた最後の警告状態をポップします。 *プッシュ*と*pop*の間で警告状態に加えた変更は元に戻されます。 次の例について考えます。

```cpp
#pragma warning( push )
#pragma warning( disable : 4705 )
#pragma warning( disable : 4706 )
#pragma warning( disable : 4707 )
// Some code
#pragma warning( pop )
```

このコードの最後では、 ** すべての警告 (4705、4706、および4707を含む) の状態が、コードの先頭にあるものに復元されます。

ヘッダーファイルを記述するときに、*プッシュ*と*pop*を使用して、ユーザーが行った警告状態の変更によって、ヘッダーが正しくコンパイルされないようにすることができます。 ヘッダーの先頭で*push*を使用し、最後に*ポップ*します。 たとえば、警告レベル4で正常にコンパイルされないヘッダーがある場合、次のコードは警告レベルを3に変更し、ヘッダーの最後に元の警告レベルを復元します。

```cpp
#pragma warning( push, 3 )
// Declarations/definitions
#pragma warning( pop )
```

警告を抑制するために役立つコンパイラオプションの詳細については、「 [/fi](../build/reference/fi-name-forced-include-file.md)と[/w](../build/reference/compiler-option-warning-level.md)」を参照してください。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと __ プラグマキーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
