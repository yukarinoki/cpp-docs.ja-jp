---
description: 詳細については、「dllexport、dllimport」を参照してください。
title: dllexport、dllimport
ms.date: 11/04/2016
f1_keywords:
- dllimport_cpp
- dllexport_cpp
helpviewer_keywords:
- dllexport __declspec keyword
- __declspec keyword [C++], dllexport
- dllimport __declspec keyword
- __declspec keyword [C++], dllimport
ms.assetid: ff95b645-ef55-4e72-b848-df44657b3208
ms.openlocfilehash: 7147aa07d5579a61a2913fcc0beb85634dc1d8df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195505"
---
# <a name="dllexport-dllimport"></a>dllexport、dllimport

**Microsoft 固有の仕様**

**`dllexport`** および **`dllimport`** ストレージクラス属性は、C および C++ 言語に対する Microsoft 固有の拡張機能です。 それらの属性を使用すると、関数、データ、オブジェクトを DLL との間でエクスポートおよびインポートできます。

## <a name="syntax"></a>構文

```
   __declspec( dllimport ) declarator
   __declspec( dllexport ) declarator
```

## <a name="remarks"></a>解説

これらの属性は、DLL のクライアント (実行可能ファイルまたは別の DLL) に対する DLL のインターフェイスを明示的に定義します。 関数をとして宣言すると、 **`dllexport`** 少なくともエクスポートされた関数の仕様に関して、モジュール定義 (.def) ファイルが不要になります。 属性は、 **`dllexport`** **__export** キーワードを置き換えます。

クラスを declspec(dllexport) とマークした場合、そのクラス階層内のクラス テンプレートの特殊化は暗黙的に declspec(dllexport) とマークされます。 つまり、クラス テンプレートが明示的にインスタンス化され、クラスのメンバーの定義が必要になります。

**`dllexport`** 関数のは、その装飾名を使用して関数を公開します。 C++ の関数の場合、この処理には名前のマングルが含まれます。 C 関数または `extern "C"` として宣言されている関数の場合、この処理には呼び出し規則に基づいたプラットフォーム固有の装飾が含まれます。 C/c + + コードでの名前の装飾については、「 [装飾名](../build/reference/decorated-names.md)」を参照してください。 `extern "C"`呼び出し規約を使用して、エクスポートされた C 関数または C++ 関数に名前の装飾は適用されません **`__cdecl`** 。

修飾されていない名前をエクスポートするには、EXPORTS セクションに非装飾名を定義したモジュール定義 (.def) ファイルを使用してリンクできます。 詳細については、「 [エクスポート](../build/reference/exports.md)」を参照してください。 装飾されていない名前をエクスポートするもう1つの方法は、 `#pragma comment(linker, "/export:alias=decorated_name")` ソースコードでディレクティブを使用することです。

**`dllexport`** またはを宣言する場合は、 **`dllimport`** [拡張属性構文](../cpp/declspec.md)とキーワードを使用する必要があり **`__declspec`** ます。

## <a name="example"></a>例

```cpp
// Example of the dllimport and dllexport class attributes
__declspec( dllimport ) int i;
__declspec( dllexport ) void func();
```

または、コードをより読みやすくするために、マクロ定義を使用できます。

```cpp
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport void func();
DllExport int i = 10;
DllImport int j;
DllExport int n;
```

詳細については、次を参照してください。

- [定義と宣言](../cpp/definitions-and-declarations-cpp.md)

- [Dllexport および dllimport を使用したインライン C++ 関数の定義](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

- [一般的な規則と制限事項](../cpp/general-rules-and-limitations.md)

- [C++ クラスでの dllimport と dllexport の使用](../cpp/using-dllimport-and-dllexport-in-cpp-classes.md)

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
