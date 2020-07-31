---
title: CL のコマンド ファイル
description: MSVC コンパイラを使用すると、コマンドラインオプションを含むコマンドファイルを指定できます。
ms.date: 07/08/2020
helpviewer_keywords:
- cl.exe compiler, command files
- command files
- command files, CL compiler
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
ms.openlocfilehash: 6deab4b11dcc6c53beb5b4fa8b014a56020c3420
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180943"
---
# <a name="cl-command-files"></a>CL のコマンド ファイル

コマンドファイルは、コンパイラオプションとファイル名を含むテキストファイルです。 それ以外の場合は、[コマンドライン](compiler-command-line-syntax.md)で入力するオプションを指定するか、[環境変数 CL](cl-environment-variables.md)を使用して指定します。 CL では、コンパイラコマンドファイルを引数として、CL 環境変数またはコマンドラインで指定できます。 コマンドラインまたは CL 環境変数とは異なり、コマンドファイルでは複数行のオプションとファイル名を使用できます。

コマンドファイル内のオプションとファイル名は、コマンド名が CL 環境変数またはコマンドライン内にあるときに処理されます。 ただし、 **`/link`** コマンドファイルにオプションが表示されている場合は、行の残りのすべてのオプションがリンカーに渡されます。 コマンドファイルの後の行のオプション、およびコマンドファイルの呼び出し後のコマンドラインのオプションは、コンパイラオプションとして引き続き受け入れられます。 オプションの順序が解釈に与える影響の詳細については、「 [CL オプションの順序](order-of-cl-options.md)」を参照してください。

コマンドファイルには、CL コマンドを含めることはできません。 各オプションの先頭と末尾は同じ行である必要があります。円記号 () を使用して、 **`\`** 2 つの行でオプションを結合することはできません。

コマンドファイルは、アットマーク () の後にファイル名を付けて指定し **`@`** ます。 ファイル名には、絶対パスまたは相対パスを指定できます。

たとえば、次のコマンドが RESP という名前のファイルに含まれているとします。

```cmd
/Ot /link LIBC.LIB
```

次の CL コマンドを指定します。

```cmd
CL /Ob2 @RESP MYAPP.C
```

CL のコマンドは次のとおりです。

```cmd
CL /Ob2 /Ot MYAPP.C /link LIBC.LIB
```

ここでは、コマンドラインとコマンドファイルのコマンドがどのように効果的に結合されるかを確認できます。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[MSVC コンパイラオプション](compiler-options.md)
