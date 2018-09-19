---
title: 関数を使った DLL からエクスポートする |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- dllexport
- __declspec
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- names [C++], DLL exports by
- export directives [C++]
- exporting DLLs [C++], __declspec(dllexport) keyword
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0415bf6d2019e192f60aa7796fd120f0fa8a7a67
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710477"
---
# <a name="exporting-from-a-dll-using-declspecdllexport"></a>__declspec(dllexport) を使った DLL からのエクスポート

導入された Microsoft **_ _export** 16 ビットのコンパイラ バージョンの Visual C コンパイラは、エクスポート名を自動的に生成し、.lib ファイルに配置します。 この .lib ファイルは、DLL とリンクするスタティック ライブラリと同じように使用できます。

新しいバージョンのコンパイラからエクスポートできますデータ、関数、クラス、またはクラス メンバー関数を使用して、DLL、**方式**キーワード。 **方式**.def ファイルを使用する必要はありませんので、オブジェクト ファイルにエクスポート ディレクティブを追加します。

この機能は、C++ 関数の装飾名をエクスポートする場合に特に便利です。 名前の装飾には標準仕様がないので、エクスポート関数の名前は、コンパイラのバージョン間で変わる場合があります。 使用する場合**方式**アカウントにのみ、名前付け規約の変更のために必要なは、DLL と従属する .exe ファイルを再コンパイルします。

序数、NONAME、PRIVATE など、多くのエクスポート ディレクティブは、.def ファイル内にしか作成されないので、これらの属性を .def ファイルを使用せずに指定することはできません。 ただしを使用して**方式**に加えて、.def ファイルはしないビルド エラーが発生します。

関数をエクスポートする、**方式**キーワードはキーワードが指定されている場合、呼び出し規約キーワードの左側に表示する必要があります。 例えば:

```
__declspec(dllexport) void __cdecl Function1(void);
```

クラス内のすべてのパブリック データ メンバーおよびメンバー関数をエクスポートするには、次のように、クラス名の左にキーワードを記述します。

```
class __declspec(dllexport) CExampleExport : public CObject
{ ... class definition ... };
```

> [!NOTE]
>  `__declspec(dllexport)` は、`__clrcall` 呼び出し規約を伴う関数には適用できません。

通常、関数のプロトタイプやエクスポートし、追加するクラスを含むヘッダー ファイルを作成する DLL を作成するときに**方式**ヘッダー ファイル内の宣言にします。 コードを読みやすくするためのマクロを定義**方式**をエクスポートする各シンボルでマクロを使用。

```
#define DllExport   __declspec( dllexport )
```

**方式**ストア機能の DLL のエクスポート テーブル内の名前。 テーブルのサイズを最適化する場合を参照してください。[関数ではなく序数値の名前を DLL からエクスポート](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)します。

> [!NOTE]
>  Win16 から Win32 への DLL ソース コードを移植するときの各インスタンスを置き換える **_ _export**で**方式**します。

参考として、Win32 の Winbase.h ヘッダー ファイルを検索してください。 例が含まれている **_declspec**使用量。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [.Def ファイルを使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-def-files.md)

- [AFX_EXT_CLASS を使ったエクスポート/インポート](../build/exporting-and-importing-using-afx-ext-class.md)

- [C 言語の実行可能ファイルで使用するための C++ 関数をエクスポートします。](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C または C++ 言語の実行可能ファイルで使用するための C 関数をエクスポートします。](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [エクスポート方式の使用](../build/determining-which-exporting-method-to-use.md)

- [使用してアプリケーションをインポートします。](../build/importing-into-an-application-using-declspec-dllimport.md)

- [DLL を初期化します。](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [_ _Declspec キーワード](../cpp/declspec.md)

- [インポートとエクスポートのインライン関数](../build/importing-and-exporting-inline-functions.md)

- [相互インポート](../build/mutual-imports.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](../build/exporting-from-a-dll.md)