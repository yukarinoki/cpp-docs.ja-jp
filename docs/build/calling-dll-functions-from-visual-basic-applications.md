---
title: Visual Basic アプリケーションから DLL 関数を呼び出す |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], calling DLL functions from Visual Basic
- DLL functions [C++]
- function calls [C++], DLL functions
- DLLs [C++], calling
- calling DLL functions from VB applications [C++]
- __stdcall keyword [C++]
- DLL functions [C++], calling
ms.assetid: 282f7fbf-a0f2-4b9f-b277-1982710be56c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9877544635dc894bbe379c751de35297add91c9d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367083"
---
# <a name="calling-dll-functions-from-visual-basic-applications"></a>DLL 関数の Visual Basic アプリケーションからの呼び出し方
VBA (Visual Basic アプリケーション) や Pascal、Fortran などの他の言語で書かれたアプリケーションから C/C++ DLL 内の関数を呼び出すには、コンパイラによって装飾された名前ではなく正しい呼び出し規則を使ってその関数をエクスポートする必要があります。  
  
 `__stdcall` は、関数の正しい呼び出し規約を作成します。つまり、呼び出された関数がスタックをクリアし、パラメーターは右から左へ渡されます。ただし、関数名は異なる方法で装飾されます。 ときに、**方式**使用 DLL でエクスポートされた関数の装飾名がエクスポートされます。  
  
 `__stdcall` 方式で装飾された名前には、シンボル名の前に _ (アンダースコア)、シンボルの後に @ (アット マーク) が付けられ、その後に引数リストのバイト数 (必要なスタック空間) が付けられます。 結果として、宣言時の関数は次のようになります。  
  
```  
int __stdcall func (int a, double b)  
```  
  
 これを装飾すると、次のようになります。  
  
```  
_func@12  
```  
  
 C の呼び出し規約 (`__cdecl`) による装飾では、名前は `_func` となります。  
  
 装飾名を取得する[/map](../build/reference/map-generate-mapfile.md)です。 使用**方式**は次の実行します。  
  
-   C 呼び出し規約と関数をエクスポートするかどうか (**_cdecl**)、名前をエクスポートするときに、先頭にアンダー スコア (_) を削除します。  
  
-   エクスポートされる関数が C の呼び出し規約を使わない場合 (`__stdcall` など) は、装飾名がエクスポートされます。  
  
 スタックがクリアされた場所をオーバーライドする方法はないので、`__stdcall` を使う必要があります。 `__stdcall` を使って装飾を外すには、.def ファイルの EXPORTS セクションにエイリアスを使って、その名前を指定する必要があります。 関数宣言の例を次に示します。  
  
```  
int  __stdcall MyFunc (int a, double b);  
void __stdcall InitCode (void);  
```  
  
 .DEF ファイルの内容は、次のとおりです。  
  
```  
EXPORTS  
   MYFUNC=_MyFunc@12  
   INITCODE=_InitCode@0  
```  
  
 Visual Basic で書かれたプログラムから DLL を呼び出す場合は、ここで示したエイリアスの手法を .def ファイル内で使用する必要があります。 エイリアスが Visual Basic プログラムの中で宣言されている場合は、.def ファイル内でのエイリアスは不要です。 Visual Basic プログラムにエイリアス句を追加することによって行うことができます、 [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement)ステートメントです。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [DLL からのエクスポート](../build/exporting-from-a-dll.md)  
  
-   [使用して DLL からエクスポートしています。DEF ファイル](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [関数を使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [C 言語の実行可能ファイルで使用するための C++ 関数をエクスポートします。](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [エクスポート方式の使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [装飾名](../build/reference/decorated-names.md)  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)