---
title: MSVC コンパイラ コマンド ラインの構文
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
ms.openlocfilehash: 6a56474b537d78a3d0bea8a74d9082007cd2e295
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320545"
---
# <a name="compiler-command-line-syntax"></a>コンパイラ コマンド ラインの構文

CL コマンド・ラインでは、次の構文を使用します。

```
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]
```

次の表は、CL コマンドへの入力について説明しています。

|エントリ|意味|
|-----------|-------------|
|*オプション*|1 つ以上の[CL オプション](compiler-options.md): すべてのオプションは、指定したすべてのソースファイルに適用されることに注意してください。 オプションは、スラッシュ (/) またはダッシュ (-) で指定します。 オプションが引数を取る場合、オプションの説明は、オプションと引数の間にスペースが許可されているかどうかを示します。 オプション名 (/HELP オプションを除く) では、大文字と小文字が区別されます。 詳細については[、CL オプションの順序](order-of-cl-options.md)を参照してください。|
|`file`|1 つ以上のソース ファイル、.obj ファイル、またはライブラリの名前。 CL はソース ファイルをコンパイルし、.obj ファイルとライブラリの名前をリンカーに渡します。 詳細については[、CL ファイル名の構文](cl-filename-syntax.md)を参照してください。|
|*Lib*|1 つ以上のライブラリ名。 CL は、これらの名前をリンカーに渡します。|
|*コマンド ファイル*|複数のオプションとファイル名を含むファイル。 詳細については[、CL コマンド・ファイル](cl-command-files.md)を参照してください。|
|*リンクオプト*|1 つ以上[の MSVC リンカ オプション](linker-options.md)。 CL は、これらのオプションをリンカーに渡します。|

コマンド ラインの文字数が 1024 文字を超えない限り、オプション、ファイル名、およびライブラリ名をいくつでも指定できます。

cl.exe の戻り値については[、「cl.exe の戻り値](return-value-of-cl-exe.md)」を参照してください。

> [!NOTE]
> コマンド ライン入力の制限値 1024 文字は、Windows の将来のリリースで同じままであるとは限りません。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)
