---
title: エクスポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- EXPORTS
dev_langs:
- C++
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cc7a9995fdc5be786712752e30015337b9f1607
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376827"
---
# <a name="exports"></a>EXPORTS
関数またはデータのエクスポート名または序数を指定する 1 つ以上のエクスポート定義のセクションを導入します。 各定義は個別の行に指定する必要があります。  
  
```  
EXPORTS  
   definition  
```  
  
## <a name="remarks"></a>コメント  
 最初の `definition` は、`EXPORTS` キーワードと同じ行か後続の行に指定できます。 .DEF ファイルには、1 つ以上の `EXPORTS` ステートメントを含めることができます。  
  
 エクスポートの `definition` の構文は次のとおりです。  
  
```  
  
entryname[=internalname] [@ordinal [NONAME]] [[PRIVATE] | [DATA]]  
```  
  
 `entryname` は、エクスポートする関数名または変数名です。 これは必須です。 エクスポートする名前が DLL 内の名前と異なる場合は、`internalname` を使用して DLL でのエクスポートの名前を指定します。 たとえば、DLL で関数 `func1` をエクスポートし、呼び出し元がそれを `func2` として使用する場合は、次のように指定します。  
  
```  
EXPORTS  
   func2=func1  
```  
  
 Visual C++ コンパイラでは C++ 関数の名前の装飾が使用されるため、`entryname` または `internalname` として装飾名を使用するか、ソース コードで `extern "C"` を使用してエクスポート関数を定義する必要があります。 コンパイラが使用する C 関数を装飾も、 [_ _stdcall](../../cpp/stdcall.md)呼び出し規約、アンダー スコア (_) プレフィックスおよびサフィックスで構成をアット マーク (@) (10 進数) の引数リスト内のバイト数が続きます。  
  
 コンパイラによって生成された装飾名を検索する、 [DUMPBIN](../../build/reference/dumpbin-reference.md)ツールまたはリンカー [/map](../../build/reference/map-generate-mapfile.md)オプション。 装飾名はコンパイラ固有です。 装飾名を .DEF ファイルにエクスポートする場合、DLL にリンクする実行可能ファイルも同じバージョンのコンパイラを使用してビルドする必要があります。 これにより、呼び出し元の装飾名は .DEF ファイルのエクスポート名と一致します。  
  
 @`ordinal` を使用して、関数名ではなく番号が DLL のエクスポート テーブルに格納されるように指定できます。 多くの Windows DLL で、レガシ コードをサポートするために序数がエクスポートされます。 DLL のサイズを最小限に抑えるのに役立つため、16 ビットの Windows コードでは序数を使用することが一般的でした。 レガシ サポートのために DLL のクライアントで必要な場合を除き、関数を序数でエクスポートすることはお勧めしません。 .LIB ファイルには序数と関数のマッピングが含まれているため、DLL を使用するプロジェクトでは通常と同様に関数名を使用できます。  
  
 省略可能な `NONAME` キーワードを使用することで、序数のみでエクスポートして、生成される DLL 内のエクスポート テーブルのサイズを縮小できます。 ただし、使用する場合[GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) DLL の名前が有効でないために、序数を知る必要があります。  
  
 省略可能なキーワード `PRIVATE` を使用すると、`entryname` は LINK によって生成されるインポート ライブラリに含まれません。 同じく LINK によって生成されるイメージ内のエクスポートには影響しません。  
  
 省略可能なキーワード `DATA` によって、エクスポートがコードではなくデータであることが指定されます。 次の例では、`exported_global` という名前のデータ変数をエクスポートする方法を示します。  
  
```  
EXPORTS  
   exported_global DATA  
```  
  
 定義をエクスポートするには 4 つの方法があり、それらを推奨される順序で示します。  
  
1.  [方式](../../cpp/dllexport-dllimport.md)ソース コード内のキーワード  
  
2.  .DEF ファイルでの `EXPORTS` ステートメント  
  
3.  [/Export](../../build/reference/export-exports-a-function.md) LINK コマンド内の指定  
  
4.  A[コメント](../../preprocessor/comment-c-cpp.md)形式のソース コードにディレクティブ `#pragma comment(linker, "/export: definition ")`  
  
 同じプログラムで 4 つの方法すべてを使用できます。 エクスポートを含むプログラムが LINK によってビルドされる際に、ビルドで .EXP ファイルが使用されていない限り、インポート ライブラリも作成されます。  
  
 次に、EXPORTS セクションの例を示します。  
  
```  
EXPORTS  
   DllCanUnloadNow      @1          PRIVATE  
   DllWindowName = WindowName       DATA  
   DllGetClassObject    @4 NONAME   PRIVATE  
   DllRegisterServer    @7  
   DllUnregisterServer  
```  
  
 .DEF ファイルを使用して DLL から変数をエクスポートする場合、変数に `__declspec(dllexport)` を指定する必要はありません。 ただし、DLL を使用するファイルでは、データの宣言で `__declspec(dllimport)` を引き続き使用する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)