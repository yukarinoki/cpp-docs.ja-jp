---
title: エクスポート |Microsoft Docs
ms.custom: ''
ms.date: 08/20/2018
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
ms.openlocfilehash: f6645ee4c890dab65cde8eab5dc18df1c31082c1
ms.sourcegitcommit: 7f3df9ff0310a4716b8136ca20deba699ca86c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "42571536"
---
# <a name="exports"></a>EXPORTS

関数またはデータのエクスポート名または序数を指定する 1 つ以上のエクスポート定義のセクションを導入します。 各定義は個別の行に指定する必要があります。  
  
```DEF  
EXPORTS  
   definition  
```  
  
## <a name="remarks"></a>Remarks  

最初の*定義*と同じ行に配置できる、`EXPORTS`キーワードまたは後続の行にします。 .DEF ファイルには、1 つ以上の `EXPORTS` ステートメントを含めることができます。  
  
エクスポートの構文は、*定義*は。  
  
```DEF
entryname[=internal_name|other_module.another_exported_name] [@Ordinal [NONAME]] [[PRIVATE] | [DATA]]
```

*entryname*にエクスポートする関数または変数の名前です。 これは必須です。 DLL の名前からエクスポートする名前が異なる場合、エクスポートの名前、DLL を使用して指定*internal_name*します。 たとえば、DLL で関数 `func1` をエクスポートし、呼び出し元がそれを `func2` として使用する場合は、次のように指定します。

```DEF
EXPORTS
   func2=func1
```

エクスポートする名前が他のいくつかのモジュールからの場合は、エクスポートの名前、DLL を使用して指定*other_module.exported_name*します。 たとえば、DLL で関数 `other_module.func1` をエクスポートし、呼び出し元がそれを `func2` として使用する場合は、次のように指定します。

```DEF
EXPORTS
   func2=other_module.func1
```

序数でエクスポートする別のモジュールからエクスポートする名前がある場合の指定を使用して、エクスポートの DLL で序数に基づく*other_module。 #ordinal_number*します。 たとえば、DLL から他のモジュールでは序数の 42 し、呼び出し元として使用する関数のエクスポート`func2`、指定します。

```DEF
EXPORTS
   func2=other_module.#42
```

Visual C コンパイラでは、C++ の関数の名前の装飾を使用するため、装飾名 internal_name を使用して、いずれか、ソース コードでは、extern"C"を使用して、エクスポートされた関数を定義する必要があります。 コンパイラを使用する C 関数を装飾も、 [_ _stdcall](../../cpp/stdcall.md)呼び出し規約をアンダー スコア (_) プレフィックスとから成る、サフィックスを持つ、アット マーク (@) 後に (10 進数) で、引数リスト内のバイト数。  
  
コンパイラによって生成された装飾名を検索するには、使用、 [DUMPBIN](../../build/reference/dumpbin-reference.md)ツールまたはリンカー [/map](../../build/reference/map-generate-mapfile.md)オプション。 装飾名はコンパイラ固有です。 装飾名を .DEF ファイルにエクスポートする場合、DLL にリンクする実行可能ファイルも同じバージョンのコンパイラを使用してビルドする必要があります。 これにより、呼び出し元の装飾名は .DEF ファイルのエクスポート名と一致します。  
  
を使用することができます*序数*と関数名ではなく、数字には、DLL のエクスポート テーブルに予定を指定します。 多くの Windows DLL で、レガシ コードをサポートするために序数がエクスポートされます。 DLL のサイズを最小限に抑えるのに役立つため、16 ビットの Windows コードでは序数を使用することが一般的でした。 レガシ サポートのために DLL のクライアントで必要な場合を除き、関数を序数でエクスポートすることはお勧めしません。 .LIB ファイルには序数と関数のマッピングが含まれているため、DLL を使用するプロジェクトでは通常と同様に関数名を使用できます。  
  
省略可能な `NONAME` キーワードを使用することで、序数のみでエクスポートして、生成される DLL 内のエクスポート テーブルのサイズを縮小できます。 ただし、使用する場合[GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) DLL の名前を有効にすることはできないために、序数を知る必要があります。  
  
省略可能なキーワード`PRIVATE`防止*entryname* LINK によって生成されるインポート ライブラリに含まれるからです。 同じく LINK によって生成されるイメージ内のエクスポートには影響しません。  
  
省略可能なキーワード `DATA` によって、エクスポートがコードではなくデータであることが指定されます。 次の例では、`exported_global` という名前のデータ変数をエクスポートする方法を示します。  
  
```DEF  
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
  
```DEF  
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
