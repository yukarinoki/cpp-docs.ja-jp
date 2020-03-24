---
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
ms.openlocfilehash: 0a8d90770552b8b9ab9169378289108d91811216
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189456"
---
# <a name="dllexport-dllimport"></a>dllexport、dllimport

**Microsoft 固有の仕様**

**Dllexport**および**dllimport**ストレージクラス属性は、C とC++言語に対する Microsoft 固有の拡張機能です。 それらの属性を使用すると、関数、データ、オブジェクトを DLL との間でエクスポートおよびインポートできます。

## <a name="syntax"></a>構文

```
   __declspec( dllimport ) declarator
   __declspec( dllexport ) declarator
```

## <a name="remarks"></a>解説

これらの属性は、DLL のクライアント (実行可能ファイルまたは別の DLL) に対する DLL のインターフェイスを明示的に定義します。 関数を**dllexport**として宣言すると、少なくともエクスポートされた関数の仕様に関して、モジュール定義 (.def) ファイルが不要になります。 **Dllexport**属性は **__export**キーワードを置き換えます。

クラスを declspec(dllexport) とマークした場合、そのクラス階層内のクラス テンプレートの特殊化は暗黙的に declspec(dllexport) とマークされます。 つまり、クラス テンプレートが明示的にインスタンス化され、クラスのメンバーの定義が必要になります。

関数の**dllexport**は、その装飾名を使用して関数を公開します。 C++ の関数の場合、この処理には名前のマングルが含まれます。 C 関数または `extern "C"` として宣言されている関数の場合、この処理には呼び出し規則に基づいたプラットフォーム固有の装飾が含まれます。 C/C++コードでの名前の装飾の詳細については、「[装飾名](../build/reference/decorated-names.md)」を参照してください。 `extern "C"` 呼び出し規則を使用する エクスポートされた C 関数や C++ `__cdecl` 関数には、名前の装飾が適用されません。

修飾されていない名前をエクスポートするには、EXPORTS セクションに非装飾名を定義したモジュール定義 (.def) ファイルを使用してリンクできます。 詳細については、「[エクスポート](../build/reference/exports.md)」を参照してください。 装飾されていない名前をエクスポートするもう1つの方法は、ソースコードで `#pragma comment(linker, "/export:alias=decorated_name")` ディレクティブを使用することです。

**Dllexport**または**dllimport**を宣言する場合は、[拡張属性構文](../cpp/declspec.md)と **__declspec**キーワードを使用する必要があります。

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

- [dllexport と dllimport を使用したインライン C 関数の定義](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

- [一般的な規則と制約](../cpp/general-rules-and-limitations.md)

- [C++ クラスでの dllimport と dllexport の使用](../cpp/using-dllimport-and-dllexport-in-cpp-classes.md)

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
