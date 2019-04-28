---
title: __declspec(dllexport) を使った DLL からのエクスポート
ms.date: 11/04/2016
f1_keywords:
- dllexport
- __declspec
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- names [C++], DLL exports by
- export directives [C++]
- exporting DLLs [C++], __declspec(dllexport) keyword
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
ms.openlocfilehash: 3b6b9733776f30fc8dcbfeee709b7d24e0f0187b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195317"
---
# <a name="exporting-from-a-dll-using-declspecdllexport"></a>__declspec(dllexport) を使った DLL からのエクスポート

導入された Microsoft **_ _export**ビジュアルの 16 ビットのコンパイラのバージョンでC++コンパイラは、エクスポート名を自動的に生成し、.lib ファイルに配置します。 この .lib ファイルは、DLL とリンクするスタティック ライブラリと同じように使用できます。

新しいバージョンのコンパイラからエクスポートできますデータ、関数、クラス、またはクラス メンバー関数を使用して、DLL、**方式**キーワード。 **方式**.def ファイルを使用する必要はありませんので、オブジェクト ファイルにエクスポート ディレクティブを追加します。

この機能は、C++ 関数の装飾名をエクスポートする場合に特に便利です。 名前の装飾には標準仕様がないので、エクスポート関数の名前は、コンパイラのバージョン間で変わる場合があります。 使用する場合**方式**アカウントにのみ、名前付け規約の変更のために必要なは、DLL と従属する .exe ファイルを再コンパイルします。

序数、NONAME、PRIVATE など、多くのエクスポート ディレクティブは、.def ファイル内にしか作成されないので、これらの属性を .def ファイルを使用せずに指定することはできません。 ただしを使用して**方式**に加えて、.def ファイルはしないビルド エラーが発生します。

関数をエクスポートする、**方式**キーワードはキーワードが指定されている場合、呼び出し規約キーワードの左側に表示する必要があります。 例:

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

通常、関数のプロトタイプやエクスポートし、追加するクラスを含むヘッダー ファイルを作成する DLL を作成するときに**方式**ヘッダー ファイル内の宣言にします。 コードを読みやすくするためのマクロを定義**方式**をエクスポートする各シンボルでマクロを使用。

```
#define DllExport   __declspec( dllexport )
```

**方式**ストア機能の DLL のエクスポート テーブル内の名前。 テーブルのサイズを最適化する場合を参照してください。[関数ではなく序数値の名前を DLL からエクスポート](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)します。

> [!NOTE]
>  Win16 から Win32 への DLL ソース コードを移植するときの各インスタンスを置き換える **_ _export**で**方式**します。

参考として、Win32 の Winbase.h ヘッダー ファイルを検索してください。 例が含まれている **_declspec**使用量。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [.Def ファイルを使った DLL からエクスポートします。](exporting-from-a-dll-using-def-files.md)

- [AFX_EXT_CLASS を使ったエクスポート/インポート](exporting-and-importing-using-afx-ext-class.md)

- [C 言語の実行可能ファイルで使用するための C++ 関数をエクスポートします。](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C または C++ 言語の実行可能ファイルで使用するための C 関数をエクスポートします。](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [エクスポート方式の使用](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

- [DLL を初期化します。](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [_ _Declspec キーワード](../cpp/declspec.md)

- [インライン関数のインポートとエクスポート](importing-and-exporting-inline-functions.md)

- [相互インポート](mutual-imports.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](exporting-from-a-dll.md)
