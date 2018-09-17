---
title: CL コマンド ファイル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, command files
- command files
- command files, CL compiler
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8458462304a9b739c61997505724d21bb56763f6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45708671"
---
# <a name="cl-command-files"></a>CL のコマンド ファイル

コマンド ファイルは、オプションとそれ以外の場合に入力したファイル名を含むテキスト ファイル、[コマンドライン](../../build/reference/compiler-command-line-syntax.md)または指定を使用して、[環境変数 CL](../../build/reference/cl-environment-variables.md)します。 CL は、環境変数 CL またはコマンドラインで引数としてのコンパイラ コマンド ファイルを受け取ります。 コマンド ラインまたは環境変数 CL ではオプションとファイル名を 1 行しか指定できませんが、コマンド ファイルでは複数行指定できます。

オプションとコマンド ファイル内のファイル名は、環境変数 CL またはコマンドラインでコマンド ファイル名の場所に従って処理されます。 ただし、/link オプションは、コマンド ファイルが表示されたら、行の残りのすべてのオプションがリンカーに渡されます。 コマンド ファイル内の後続の行のオプションとコマンド ファイルの呼び出しの後にコマンド ライン オプションは、まだコンパイラ オプションとして受け入れられます。 オプションの順序がその解釈に与える影響の詳細については、次を参照してください。 [CL オプションの指定順序](../../build/reference/order-of-cl-options.md)します。

コマンド ファイルでは、CL コマンドを含めることはできません。 各オプションの開始し、同じ行で終了する必要があります。円記号を使用することはできません (**\\**) 行に 2 つのオプションを結合します。

コマンド ファイルを指定する、アット マーク (**\@**) ファイル名に続けてファイル名は、絶対または相対パスを指定できます。

たとえば、RESP という名前のファイルが、次のコマンドの場合。

```
/Og /link LIBC.LIB
```

次のような CL コマンドを指定します。

```
CL /Ob2 @RESP MYAPP.C
```

CL のコマンドは次のとおりです。

```
CL /Ob2 /Og MYAPP.C /link LIBC.LIB
```

コマンドラインおよびコマンド ファイルが効果的にまとめられることに注意してください。

## <a name="see-also"></a>関連項目

[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)