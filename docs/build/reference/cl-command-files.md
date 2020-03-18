---
title: CL のコマンド ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, command files
- command files
- command files, CL compiler
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
ms.openlocfilehash: 1dc2d6bffe4d0681a04b875383215a0bbfc1a720
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440267"
---
# <a name="cl-command-files"></a>CL のコマンド ファイル

コマンドファイルは、[コマンドライン](compiler-command-line-syntax.md)に入力するオプションやファイル名が含まれているテキストファイルです。また、 [CL 環境変数](cl-environment-variables.md)を使用して指定することもできます。 CL では、コンパイラコマンドファイルを引数として CL 環境変数またはコマンドラインで受け取ることができます。 コマンド ラインまたは環境変数 CL ではオプションとファイル名を 1 行しか指定できませんが、コマンド ファイルでは複数行指定できます。

コマンドファイル内のオプションとファイル名は、CL 環境変数またはコマンドライン内のコマンドファイル名の場所に従って処理されます。 ただし、コマンドファイルに/link オプションが指定されている場合は、行の残りのすべてのオプションがリンカーに渡されます。 コマンドファイル内の後続の行のオプションと、コマンドファイルの呼び出し後のコマンドラインのオプションは、コンパイラオプションとしても受け入れられます。 オプションの順序が解釈に与える影響の詳細については、「 [CL オプションの順序](order-of-cl-options.md)」を参照してください。

コマンドファイルには、CL コマンドを含めることはできません。 各オプションの先頭と末尾は同じ行である必要があります。円記号 ( **\\** ) を使用して、2つの行でオプションを結合することはできません。

コマンドファイルは、アットマーク ( **\@** ) とファイル名の順で指定されます。ファイル名には、絶対パスまたは相対パスを指定できます。

たとえば、次のコマンドが RESP という名前のファイルに含まれているとします。

```
/Og /link LIBC.LIB
```

次の CL コマンドを指定します。

```
CL /Ob2 @RESP MYAPP.C
```

CL のコマンドは次のとおりです。

```
CL /Ob2 /Og MYAPP.C /link LIBC.LIB
```

コマンドラインとコマンドファイルのコマンドは、効果的に結合されることに注意してください。

## <a name="see-also"></a>参照

[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)
