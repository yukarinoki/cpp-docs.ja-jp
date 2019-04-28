---
title: warning
ms.date: 11/04/2016
f1_keywords:
- warning_CPP
- vc-pragma.warning
helpviewer_keywords:
- pragmas, warning
- push pragma warning
- pop warning pragma
- warning pragma
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
ms.openlocfilehash: 1341472af22582635207a2bdff93b4367fd59330
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179933"
---
# <a name="warning-pragma"></a>warning プラグマ
コンパイラの警告メッセージの動作の選択的な変更を有効にします。

## <a name="syntax"></a>構文

```
#pragma warning(
    warning-specifier : warning-number-list [; warning-specifier : warning-number-list...] )
#pragma warning( push[ ,n ] )
#pragma warning( pop )
```

## <a name="remarks"></a>Remarks

次の警告指定子パラメーターを使用できます。

|警告指定子|説明|
|------------------------|-------------|
|*1, 2, 3, 4*|指定された警告に特定のレベルを適用します。 これは、既定で無効になっている指定された警告も有効にします。|
|*default*|警告の動作を既定値にリセットします。 これは、既定で無効になっている指定された警告も有効にします。 警告は、既定の文書化されたレベルで生成されます。<br /><br /> 詳細については、「 [Compiler Warnings That Are Off by Default](../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。|
|*disable*|指定した警告メッセージを発行しません。|
|*error*|指定した警告をエラーとして報告します。|
|*once*|指定したメッセージを 1 回だけ表示します。|
|*非表示します。*|プラグマの現在の状態をスタックにプッシュし、次の行に対して指定された警告を無効にします。次に、プラグマの状態がリセットされるように警告スタックをポップします。|

次のコード ステートメントは、`warning-number-list` パラメーターが複数の警告の数を含むことができること、および複数の `warning-specifier` パラメーターが同じプラグマ ディレクティブで指定できることを示しています。

```cpp
#pragma warning( disable : 4507 34; once : 4385; error : 164 )
```

これは、次のコードと機能的に同等です。

```cpp
// Disable warning messages 4507 and 4034.
#pragma warning( disable : 4507 34 )

// Issue warning 4385 only once.
#pragma warning( once : 4385 )

// Report warning 4164 as an error.
#pragma warning( error : 164 )
```

コンパイラは、0 と 999 の間の任意の警告番号に 4000 を追加します。

コードの生成に関連する 4700 ～ 4999 の警告番号の場合、コンパイラで関数の左中かっこが検出された場合の有効な警告の状態は、他の関数に対しても有効になります。 使用して、**警告**プラグマ番号が 4699 より大きい警告の状態を変更する関数でのみ有効になる関数の終了後にします。 次の例は、適切な配置の**警告**プラグマ、コード生成の警告メッセージを無効にし、それを復元します。

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

関数全体で本文などの最後の設定、**警告**プラグマは関数全体に対して有効になります。

## <a name="push-and-pop"></a>プッシュおよびポップ

**警告**プラグマは、次の構文もサポートしています。 ここ*n*警告レベル (1 ~ 4) を表します。

`#pragma warning( push [ , n ] )`

`#pragma warning( pop )`

プラグマ`warning( push )`すべての警告の現在の警告状態を格納します。 プラグマ`warning( push, n )`すべての警告の現在の状態を格納し、グローバル警告レベルを設定*n*します。

プラグマ`warning( pop )`pop の最後の警告状態をスタックにプッシュします。 間の警告状態に対して行った変更を加えた*プッシュ*と*pop*は取り消されます。 次の例について考えます。

```cpp
#pragma warning( push )
#pragma warning( disable : 4705 )
#pragma warning( disable : 4706 )
#pragma warning( disable : 4707 )
// Some code
#pragma warning( pop )
```

、このコードの最後に*pop*すべての警告の状態を復元します (4705、4706、および 4707 が含まれています)、コードの開始時にします。

ヘッダー ファイルを記述するときに使用できます*プッシュ*と*pop*ことをユーザーが行った警告状態の変更が妨げられないヘッダー正しくコンパイルすることを保証します。 使用*プッシュ*ヘッダーの開始時と*pop*最後にします。 たとえば、警告レベル 4 で正しくコンパイルされていないヘッダーがある場合は、次のコードで警告レベルを 3 に変更し、ヘッダーの終わりで元の警告レベルを復元します。

```cpp
#pragma warning( push, 3 )
// Declarations/definitions
#pragma warning( pop )
```

警告を参照する際に役立つオプションを抑制するコンパイラの詳細については[/FI](../build/reference/fi-name-forced-include-file.md)と[/w](../build/reference/compiler-option-warning-level.md)します。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)