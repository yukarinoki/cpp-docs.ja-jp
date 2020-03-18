---
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
ms.openlocfilehash: c84a8eca25c90e0790ec8c4991d9d5a116afa59f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442528"
---
# <a name="exporting-from-a-dll-using-__declspecdllexport"></a>__declspec(dllexport) を使った DLL からのエクスポート

データ、関数、クラス、またはクラスメンバー関数を DLL からエクスポートするには、 **__declspec (dllexport)** キーワードを使用します。 **__declspec (dllexport)** は、.def ファイルを使用する必要がないように、export ディレクティブをオブジェクトファイルに追加します。

この機能は、C++ 関数の装飾名をエクスポートする場合に特に便利です。 名前の装飾には標準仕様がないので、エクスポート関数の名前は、コンパイラのバージョン間で変わる場合があります。 **__Declspec (dllexport)** を使用する場合は、DLL と依存する .exe ファイルを再コンパイルするだけで、名前付け規則の変更を考慮する必要があります。

序数、NONAME、PRIVATE など、多くのエクスポート ディレクティブは、.def ファイル内にしか作成されないので、これらの属性を .def ファイルを使用せずに指定することはできません。 ただし、.def ファイルを使用するだけでなく **__declspec (dllexport)** を使用しても、ビルドエラーは発生しません。

関数をエクスポートするには、キーワードが指定されている場合、呼び出し規約キーワードの左側に **__declspec (dllexport)** キーワードを指定する必要があります。 例 :

```
__declspec(dllexport) void __cdecl Function1(void);
```

クラス内のすべてのパブリック データ メンバーおよびメンバー関数をエクスポートするには、次のように、クラス名の左にキーワードを記述します。

```
class __declspec(dllexport) CExampleExport : public CObject
{ ... class definition ... };
```

> [!NOTE]
>  `__declspec(dllexport)` は、`__clrcall` 呼び出し規則を伴う関数には適用できません。

DLL をビルドする場合、通常は、エクスポートする関数プロトタイプやクラスを含むヘッダーファイルを作成し、ヘッダーファイルの宣言に **__declspec (dllexport)** を追加します。 コードを読みやすくするには、 **__declspec (dllexport)** 用のマクロを定義し、エクスポートするシンボルごとにマクロを使用します。

```
#define DllExport   __declspec( dllexport )
```

**__declspec (dllexport)** は、関数名を DLL のエクスポートテーブルに格納します。 テーブルのサイズを最適化する場合は、「[名前ではなく序数による DLL からの関数のエクスポート](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)」を参照してください。

## <a name="what-do-you-want-to-do"></a>作業内容

- [.Def ファイルを使用した DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)

- [AFX_EXT_CLASS を使用したエクスポートとインポート](exporting-and-importing-using-afx-ext-class.md)

- [C C++言語の実行可能ファイルで使用するエクスポート関数](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C またはC++言語の実行可能ファイルで使用する c 関数をエクスポートする](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [使用するエクスポート方法を決定する](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [__Declspec キーワード](../cpp/declspec.md)

- [インライン関数のインポートとエクスポート](importing-and-exporting-inline-functions.md)

- [相互インポート](mutual-imports.md)

## <a name="see-also"></a>参照

[DLL からのエクスポート](exporting-from-a-dll.md)
