---
title: リンカーを呼び出す CL |Microsoft ドキュメント
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
- compiling source code [C++], without linking
- invoking linker from the compiler
- LINK tool [C++], invoking from CL compiler
- cl.exe compiler [C++], compiling without linking
- cl.exe compiler [C++], controlling linker
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc9c5c4815dc83b37d0b7971d5fd0f31db51e39e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371916"
---
# <a name="cl-invokes-the-linker"></a>リンカーを呼び出す CL
CL/c オプションを使用しない場合にコンパイルした後、リンカーによって自動的に起動します。 CL は、コンパイル時に作成された .obj ファイルの名前と、コマンドラインで指定したその他のファイルの名前をリンカーに渡します。 リンカーは、環境変数 LINK に示すオプションを使用します。 /Link オプションを使用すると、CL のコマンド ラインでリンカー オプションを指定します。 環境変数 LINK に/link オプションを次のオプションをオーバーライドします。 次の表に、オプションでは、リンクを抑制します。  
  
|オプション|説明|  
|------------|-----------------|  
|/c|リンクせずにコンパイルします。|  
|/E、/EP/P|コンパイルとリンクなしの前処理します。|  
|/Zg|関数プロトタイプを生成します。|  
|/Zs|構文を確認します。|  
  
 リンクの詳細については、次を参照してください。[リンカー オプション](../../build/reference/linker-options.md)です。  
  
## <a name="example"></a>例  
 次の 3 つの C ソース ファイルをコンパイルすることを前提としています: MAIN.c、MOD1.c、および MOD2.c です。 各ファイルには、別のファイルで定義されている関数の呼び出しが含まれます。  
  
-   MAIN.c 関数を呼び出す`func1`MOD1.c と関数で`func2`MOD2.c にします。  
  
-   MOD1.c が標準ライブラリ関数を呼び出す`printf_s`と`scanf_s`です。  
  
-   MOD2.c が名前付きグラフィックス関数を呼び出す`myline`と`mycircle`MYGRAPH.lib をという名前のライブラリで定義されています。  
  
 このプログラムをビルドするには、次のコマンドラインでコンパイルします。  
  
```  
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib  
```  
  
 まず、CL は、C ソース ファイルをコンパイルし、MAIN.obj、MOD1.obj、および MOD2.obj オブジェクト ファイルを作成します。コンパイラは、標準ライブラリの名前を各 .obj ファイルに配置します。 詳細については、次を参照してください。[ランタイム ライブラリの使用](../../build/reference/md-mt-ld-use-run-time-library.md)です。  
  
 CL は、名前、MYGRAPH.lib と共に、.obj ファイルの名前をリンカーに渡します。 リンカーは、次のように、外部参照を解決します。  
  
1.  MAIN.obj への参照で`func1`MOD1.obj; で、定義を使用して解決はへの参照を`func2`MOD2.obj の定義を使用して解決します。  
  
2.  MOD1.obj への参照で`printf_s`と`scanf_s`リンカーが検索するという名前のライブラリ MOD1.obj 内で定義を使用して解決されます。  
  
3.  MOD2.obj への参照で`myline`と`mycircle`MYGRAPH.lib の定義を使用して解決されます。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)