---
title: CL のコマンド ファイル |Microsoft ドキュメント
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
ms.openlocfilehash: 367ea6dc22777b473cad44f35b1f5e4c34528471
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="cl-command-files"></a>CL のコマンド ファイル
コマンド ファイルは、オプションとそれ以外の場合で入力するとファイル名を含むテキスト ファイル、[コマンドライン](../../build/reference/compiler-command-line-syntax.md)または指定を使用して、[環境変数 CL](../../build/reference/cl-environment-variables.md)です。 CL は、環境変数 CL またはコマンドラインで引数としてコンパイラ コマンド ファイルを受け取ります。 コマンド ラインまたは環境変数 CL ではオプションとファイル名を 1 行しか指定できませんが、コマンド ファイルでは複数行指定できます。  
  
 オプションとファイル名、コマンド ファイルには、環境変数 CL またはコマンドラインでコマンド ファイル名の場所に従って処理されます。 ただし、コマンド ファイルで、/link オプションが表示された場合は、行の残りのすべてのオプションがリンカーに渡されます。 コマンド ファイル内の後続の行にオプションおよびコマンド ファイルの呼び出しの後にコマンド ライン オプションは、まだコンパイラ オプションとして受け入れられます。 オプションの順序がその解釈に与える影響の詳細については、次を参照してください。 [CL オプションの指定順序](../../build/reference/order-of-cl-options.md)です。  
  
 コマンド ファイルでは、CL コマンドを含めることはできません。 各オプションの開始し、同じ行で終了する必要があります。バック スラッシュを使用することはできません (\\) を 2 つの行にわたってオプションを結合します。  
  
 コマンド ファイルを指定する、アット マーク (@) 後にファイル名です。ファイル名には、絶対または相対パスを指定できます。  
  
 たとえば、次のコマンドが応答するという名前のファイルの場合。  
  
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
  
 コマンドラインとコマンド ファイルが効果的に組み合わせることに注意してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)