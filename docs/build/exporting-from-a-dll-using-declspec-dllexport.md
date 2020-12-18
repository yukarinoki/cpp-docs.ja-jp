---
description: '詳細情報: __declspec(dllexport) を使った DLL からのエクスポート'
title: __declspec(dllexport) を使った DLL からのエクスポート
ms.date: 05/06/2019
f1_keywords:
- dllexport
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- names [C++], DLL exports by
- export directives [C++]
- exporting DLLs [C++], __declspec(dllexport) keyword
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
ms.openlocfilehash: e662563e63881d893b9ef717b160844e9995eb0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156542"
---
# <a name="exporting-from-a-dll-using-__declspecdllexport"></a>__declspec(dllexport) を使った DLL からのエクスポート

**`__declspec(dllexport)`** キーワードを使用すると、データ、関数、クラス、クラスのメンバー関数を DLL からエクスポートできます。 **`__declspec(dllexport)`** では、オブジェクト ファイルにエクスポート ディレクティブが追加されるので、.def ファイルを使用する必要はありません。

この機能は、C++ 関数の装飾名をエクスポートする場合に特に便利です。 名前の装飾には標準仕様がないので、エクスポート関数の名前は、コンパイラのバージョン間で変わる場合があります。 **`__declspec(dllexport)`** を使用する場合は、名前付け規則の変更に対応するためだけに、DLL とその従属する .exe ファイルを再コンパイルする必要があります。

序数、NONAME、PRIVATE など、多くのエクスポート ディレクティブは、.def ファイル内にしか作成されないので、これらの属性を .def ファイルを使用せずに指定することはできません。 ただし、.def ファイルに加えて **`__declspec(dllexport)`** を使用すると、ビルド エラーが発生しません。

関数をエクスポートするには、呼び出し規則キーワードが指定されている場合、 **`__declspec(dllexport)`** キーワードは呼び出し規則キーワードの左に記述します。 次に例を示します。

```
__declspec(dllexport) void __cdecl Function1(void);
```

クラス内のすべてのパブリック データ メンバーおよびメンバー関数をエクスポートするには、次のように、クラス名の左にキーワードを記述します。

```
class __declspec(dllexport) CExampleExport : public CObject
{ ... class definition ... };
```

> [!NOTE]
> `__declspec(dllexport)` は、`__clrcall` 呼び出し規則を伴う関数には適用できません。

DLL のビルド時には通常、エクスポートする関数のプロトタイプやクラスを含むヘッダー ファイルを作成し、そのヘッダー ファイル内の宣言に **`__declspec(dllexport)`** を追加します。 コードを読みやすくするために、次のように **`__declspec(dllexport)`** 用のマクロを定義して、そのマクロをエクスポートする各シンボルに使用します。

```
#define DllExport   __declspec( dllexport )
```

**`__declspec(dllexport)`** では、関数名は DLL のエクスポート テーブルに格納されます。 テーブル サイズの最適化方法については、「[名前ではなく序数値による DLL 関数のエクスポート](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)」を参照してください。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [.def ファイルを使用した DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)

- [AFX_EXT_CLASS を使用してエクスポートとインポートを行う](exporting-and-importing-using-afx-ext-class.md)

- [C 言語の実行可能ファイルで使用する C++ 関数をエクスポートする](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C または C++ 言語の実行可能ファイルで使用する C 関数をエクスポートする](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [エクスポート方式の使い分け](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [__declspec キーワード](../cpp/declspec.md)

- [インライン関数のインポートとエクスポート](importing-and-exporting-inline-functions.md)

- [相互インポート](mutual-imports.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](exporting-from-a-dll.md)
