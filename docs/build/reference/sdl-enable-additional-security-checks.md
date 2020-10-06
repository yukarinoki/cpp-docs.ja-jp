---
title: /sdl (追加のセキュリティ チェックの有効化)
description: Microsoft C/c + + コンパイラ/sdl オプションでは、推奨されるセキュリティ開発ライフサイクル (SDL) のチェックと警告が有効になります。
ms.date: 10/02/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.SDLCheck
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
ms.openlocfilehash: 8d679bb3fc48e52bcc42a85d507618c38fd3dcdc
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765189"
---
# <a name="sdl-enable-additional-security-checks"></a>/sdl (追加のセキュリティ チェックの有効化)

推奨されるセキュリティ開発ライフサイクル (SDL) チェックを有効にします。 これらのチェックは、セキュリティ関連の警告をエラーに変更し、セキュリティで保護された追加のコード生成機能を設定します。

## <a name="syntax"></a>構文

> **`/sdl`**[**`-`**]

## <a name="remarks"></a>解説

/ **sdl**では、によって提供されるベースラインセキュリティチェックのスーパーセットを有効にし、 [`/GS`](gs-buffer-security-check.md) 上書き **`/GS-`** します。 既定で **`/sdl`** は、はオフになっています。 **`/sdl-`** 追加のセキュリティチェックを無効にします。

### <a name="compile-time-checks"></a>コンパイル時のチェック

**`/sdl`** これらの警告をエラーとして有効にします。

| /sdl で有効になる警告 | 同等のコマンド ラインスイッチ | 説明 |
|--|--|--|
| [C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md) | /we4146 | 単項マイナス演算子が符号なしの型に適用され、符号なしの結果になります。 |
| [C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md) | /we4308 | 負の整数定数が符号なしの型に変換されて、多くの場合は意味のない結果になります。 |
| [C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md) | /we4532 | `continue`ブロック内で、、またはキーワードを使用すると、 `break` `goto` `__finally` / `finally` 異常終了時に未定義の動作が発生します。 |
| [C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md) | /we4533 | 変数の初期化コードが実行されません。 |
| [C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) | /we4700 | 初期化されていないローカル変数が使用されます。 |
| [C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md) | /we4703 | 初期化されていない可能性のあるローカル ポインター変数が使用されます。 |
| [C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md) | /we4789 | 特定の C ランタイム (CRT) 関数の使用時にバッファー オーバーランが発生します。 |
| [C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md) | /we4995 | プラグマでマークされた関数の使用 [`deprecated`](../../preprocessor/deprecated-c-cpp.md) 。 |
| [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) | /we4996 | としてマークされた関数の使用 [`deprecated`](../../cpp/deprecated-cpp.md) 。 |

### <a name="runtime-checks"></a>ランタイム チェック

を有効にすると **`/sdl`** 、コンパイラは実行時に次のチェックを実行するコードを生成します。

- **`/GS`** を使用したコンパイルと同等の、実行時のバッファーオーバーラン検出の厳格モードを有効にし `#pragma strict_gs_check(push, on)` ます。

- ポインターのサニタイズが制限されています。 逆参照を含まない式や、ユーザー定義のデストラクターを持たない型では、への呼び出しの後にポインター参照が有効でないアドレスに設定され **`delete`** ます。 このサニタイズは、古いポインター参照を再利用できないようにするために役立ちます。

- クラスメンバーポインターを初期化します。 ポインター型のクラスメンバーを **`nullptr`** オブジェクトのインスタンス化 (コンストラクターが実行される前) に自動的に初期化します。 コンストラクターが明示的に初期化しない、初期化されていないポインターの使用を防ぐのに役立ちます。 コンパイラによって生成されるメンバーポインターの初期化は、次の場合に限り呼び出されます。

  - オブジェクトはカスタム (ユーザー定義) を使用して割り当てられていません `operator new`

  - オブジェクトが配列の一部として割り当てられていない (たとえば `new A[x]` )

  - クラスはマネージまたはインポートされていません

  - クラスには、ユーザー定義の既定のコンストラクターがあります。

  コンパイラによって生成されるクラス初期化関数によって初期化されるためには、メンバーはプロパティまたは定数ではなく、ポインターである必要があります。

詳細については、「 [警告、sdl、および初期化](https://www.microsoft.com/security/blog/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/)されていない変数の検出の向上」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[C/C++]**  >  **[全般]** プロパティ ページを選択します。

1. プロパティのドロップダウンコントロールを使用して、[ **SDL のチェック** ] プロパティを設定します。 **[OK]** または [**適用**] を選択して、変更を保存します。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)
