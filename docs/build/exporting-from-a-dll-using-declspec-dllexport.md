---
title: 関数を使った DLL からエクスポート |Microsoft ドキュメント
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
ms.openlocfilehash: e6ab1d11c117c75633ce4ab836965449c4cc6ca1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368549"
---
# <a name="exporting-from-a-dll-using-declspecdllexport"></a>__declspec(dllexport) を使った DLL からのエクスポート
導入された Microsoft **_ _export**コンパイラは、エクスポート名を自動的に生成し、.lib ファイルに配置するために Visual C の 16 ビットのコンパイラのバージョンにします。 この .lib ファイルは、DLL とリンクするスタティック ライブラリと同じように使用できます。  
  
 新しいバージョンのコンパイラでからエクスポートできるデータ、関数、クラス、またはクラス メンバー関数を使用して、DLL、**方式**キーワード。 **方式**.def ファイルを使用する必要はありませんので、オブジェクト ファイルにエクスポート ディレクティブを追加します。  
  
 この機能は、C++ 関数の装飾名をエクスポートする場合に特に便利です。 名前の装飾には標準仕様がないので、エクスポート関数の名前は、コンパイラのバージョン間で変わる場合があります。 使用する場合**方式**DLL と従属する .exe ファイルを再コンパイルは、名前付け規約の変更に必要なアカウントのみにします。  
  
 序数、NONAME、PRIVATE など、多くのエクスポート ディレクティブは、.def ファイル内にしか作成されないので、これらの属性を .def ファイルを使用せずに指定することはできません。 ただしを使用して**方式**に加えて使用して、.def ファイルはエラーが発生しないビルドします。  
  
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
  
 通常関数のプロトタイプやクラスをエクスポートして、追加を含むヘッダー ファイルを作成する DLL を作成するときに**方式**ヘッダー ファイル内の宣言にします。 コードを読みやすくするためのマクロを定義**方式**しをエクスポートする各シンボルでマクロを使用します。  
  
```  
#define DllExport   __declspec( dllexport )   
```  
  
 **方式**ストア関数の DLL のエクスポート テーブル内の名前。 テーブルのサイズを最適化する場合は、「[関数ではなく序数値名によって、DLL のエクスポート](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)です。  
  
> [!NOTE]
>  移植と DLL ソース コードを Win16 から Win32 に、置換の各インスタンス **_ _export**で**方式**です。  
  
 参考として、Win32 の Winbase.h ヘッダー ファイルを検索してください。 例が含まれている **_declspec (dllimport)** 使用します。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [.Def ファイルを使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [AFX_EXT_CLASS を使ったエクスポート/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 言語の実行可能ファイルで使用するための C++ 関数をエクスポートします。](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C または C++ 言語の実行可能ファイルで使用するための C 関数をエクスポートします。](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [エクスポート方式を使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [_Declspec (dllimport) を使用してアプリケーションをインポートします。](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL を初期化します。](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [_ _Declspec キーワード](../cpp/declspec.md)  
  
-   [インポートして、インライン関数をエクスポートします。](../build/importing-and-exporting-inline-functions.md)  
  
-   [相互インポート](../build/mutual-imports.md)  
  
## <a name="see-also"></a>関連項目  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)