---
description: 詳細については、「コンパイラ Command-Line 構文」を参照してください。
title: MSVC Compiler Command-Line 構文
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
ms.openlocfilehash: 91340aa543f0e79d3071b93921742b8147918b2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182217"
---
# <a name="compiler-command-line-syntax"></a>コンパイラ コマンド ラインの構文

CL コマンドラインでは、次の構文を使用します。

```
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]
```

次の表では、CL コマンドへの入力について説明します。

|入力|説明|
|-----------|-------------|
|*オプション*|1つまたは複数の [CL オプション](compiler-options.md)。 すべてのオプションは、指定したすべてのソースファイルに適用されることに注意してください。 オプションは、スラッシュ (/) またはダッシュ (-) で指定します。 オプションが引数を受け取る場合、オプションと引数の間にスペースが許可されているかどうかは、オプションの説明によってドキュメントに記述されます。 オプション名 (/HELP オプションを除く) では、大文字と小文字が区別されます。 詳細については、「 [CL オプションの順序](order-of-cl-options.md) 」を参照してください。|
|`file`|1つ以上のソースファイル、.obj ファイル、またはライブラリの名前。 CL は、ソースファイルをコンパイルし、.obj ファイルとライブラリの名前をリンカーに渡します。 詳細については、「 [CL ファイル名の構文](cl-filename-syntax.md) 」を参照してください。|
|*変数*|1つまたは複数のライブラリ名。 CL は、これらの名前をリンカーに渡します。|
|*コマンド-ファイル*|複数のオプションとファイル名を含むファイル。 詳細については、「 [CL コマンドファイル](cl-command-files.md) 」を参照してください。|
|*リンク-選択*|1つ以上の [MSVC リンカーオプション](linker-options.md)。 CL は、これらのオプションをリンカーに渡します。|

コマンドラインの文字数が1024を超えない限り、任意の数のオプション、ファイル名、およびライブラリ名を指定できます (オペレーティングシステムによって指定された制限)。

cl.exe の戻り値の詳細については、「 [cl.exeの戻り値 ](return-value-of-cl-exe.md) 」を参照してください。

> [!NOTE]
> Windows の今後のリリースでは、1024文字のコマンドライン入力の制限が同じままであることは保証されていません。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)
