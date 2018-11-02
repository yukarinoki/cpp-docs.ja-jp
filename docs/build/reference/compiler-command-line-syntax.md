---
title: コンパイラ コマンド ラインの構文
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
ms.openlocfilehash: a350a2cb793630b90143b7d190ada9469a79bfc1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581299"
---
# <a name="compiler-command-line-syntax"></a>コンパイラ コマンド ラインの構文

CL のコマンド ラインでは、次の構文を使用します。

```
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]
```

次の表では、CL コマンドへの入力について説明します。

|入力|説明|
|-----------|-------------|
|*オプション*|1 つまたは複数[CL オプション](../../build/reference/compiler-options.md)します。 すべてのオプションは、すべての指定したソース ファイルに適用されるに注意してください。 オプションは、スラッシュ (/) またはダッシュ (-) のいずれかによって指定されます。 場合は、オプションは、オプションと引数の間に空白が許可されているかどうか、引数、オプションの説明のドキュメントを受け取ります。 (/HELP オプション) を除くオプション名は大文字小文字を区別します。 参照してください[CL オプションの指定順序](../../build/reference/order-of-cl-options.md)詳細についてはします。|
|`file`|1 つまたは複数のソース ファイル、.obj ファイル、またはライブラリの名前。 CL は、ソース ファイルをコンパイルし、.obj ファイルとライブラリの名前をリンカーに渡します。 参照してください[CL ファイル名の構文](../../build/reference/cl-filename-syntax.md)詳細についてはします。|
|*lib*|1 つまたは複数のライブラリ名。 CL は、これらの名前をリンカーに渡します。|
|*コマンド ファイル*|複数のオプションとファイル名を含むファイル。 参照してください[CL コマンド ファイル](../../build/reference/cl-command-files.md)詳細についてはします。|
|*リンクを選択します。*|1 つまたは複数[リンカー オプション](../../build/reference/linker-options.md)します。 CL は、これらのオプションをリンカーに渡します。|

コマンドラインでの文字数が 1024、オペレーティング システムで指定された制限を超えない限り、任意の数のオプション、ファイル名、およびライブラリの名前を指定できます。

Cl.exe の戻り値については、次を参照してください。 [cl.exe の戻り値](../../build/reference/return-value-of-cl-exe.md)します。

> [!NOTE]
>  1024 文字の場合は、コマンド ライン入力制限は、Windows の将来のリリースでは同じままには保証されません。

## <a name="see-also"></a>関連項目

[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)