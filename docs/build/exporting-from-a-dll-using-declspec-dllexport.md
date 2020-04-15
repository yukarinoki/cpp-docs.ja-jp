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
ms.openlocfilehash: 075962758773660085ae0b98b668c264524cc6aa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328595"
---
# <a name="exporting-from-a-dll-using-__declspecdllexport"></a>__declspec(dllexport) を使った DLL からのエクスポート

**__declspec dll**キーワードを使用して、DLL からデータ、関数、クラス、またはクラス メンバー関数をエクスポートできます。 **__declspec(dllexport) は**、エクスポート ディレクティブをオブジェクト ファイルに追加するため、.def ファイルを使用する必要はありません。

この機能は、C++ 関数の装飾名をエクスポートする場合に特に便利です。 名前の装飾には標準仕様がないので、エクスポート関数の名前は、コンパイラのバージョン間で変わる場合があります。 **__declspec(dllexport)** を使用する場合は、DLL および依存する .exe ファイルを再コンパイルする必要があるのは、名前付け規則の変更を考慮するためだけに必要です。

序数、NONAME、PRIVATE など、多くのエクスポート ディレクティブは、.def ファイル内にしか作成されないので、これらの属性を .def ファイルを使用せずに指定することはできません。 ただし、.def ファイルを使用する以外に **__declspec(dllexport)を**使用しても、ビルド エラーは発生しません。

関数をエクスポートするには、キーワードが指定されている場合は **、__declspec(dllexport)** キーワードを呼び出し規約キーワードの左側に指定する必要があります。 次に例を示します。

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

DLL をビルドする場合、通常は、エクスポートする関数プロトタイプやクラスを含むヘッダー ファイルを作成し **、__declspec(dllexport) を**ヘッダー ファイルの宣言に追加します。 コードを読みやすくするには **、__declspec(dllexport)** のマクロを定義し、エクスポートする各シンボルでマクロを使用します。

```
#define DllExport   __declspec( dllexport )
```

**__declspec(dllexport)は**、関数名を DLL のエクスポート テーブルに格納します。 テーブルのサイズを最適化する場合は、「[名前ではなく序数で DLL から関数をエクスポートする](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)」を参照してください。

## <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください

- [.def ファイルを使った DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)

- [AFX_EXT_CLASS を使ったエクスポート/インポート](exporting-and-importing-using-afx-ext-class.md)

- [C 言語の実行形式で使う C++ 関数のエクスポート](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C/C++ 言語の実行形式で使う C 関数のエクスポート](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [使用するエクスポート方法を決定する](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [__declspec キーワード](../cpp/declspec.md)

- [インライン関数のインポートとエクスポート](importing-and-exporting-inline-functions.md)

- [相互輸入](mutual-imports.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](exporting-from-a-dll.md)
