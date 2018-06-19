---
title: 相互インポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- mutual DLL imports [C++]
- AFX_DATA
- importing DLLs [C++], mutual imports
- mutually importing executable files [C++]
- AFX_EXT_CLASS macro
- circular imports
- _AFXEXT preprocessor symbol
- DLLs [C++], importing
- executable files [C++], importing
- extension DLLs [C++], mutual imports
- exporting DLLs [C++], mutual imports
ms.assetid: 2cc29537-92ee-4d92-af39-8b8b3afd808f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b43977f86be409698d8fbdba16fc63d85acfac5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377758"
---
# <a name="mutual-imports"></a>相互インポート
エクスポートまたは別の実行可能ファイルをインポートするインポートは、相互 (または循環) ときに、複雑さの一部を表示します。 たとえば、2 つの Dll は、その他の相互再帰関数のようなシンボルをインポートします。  
  
 相互インポートを実行可能ファイル (通常は Dll) に問題は、どちらを作成できる他の最初を構築することがなくです。 それぞれのビルド プロセスには、他のビルド プロセスによって生成されるインポート ライブラリが、入力として必要です。  
  
 ソリューションでは、ユーティリティを使用して、LIB/DEF オプションを使用して、実行可能ファイルを構築することがなく、インポート ライブラリを生成します。 このユーティリティを使用して、必要なすべてのインポート ライブラリをビルドすることが関連する Dll の数に関係なくや複雑さの依存関係。  
  
 相互インポートを処理するための一般的な解決方法は次のとおりです。  
  
1.  さらに各 DLL を実行します。 (任意の順序は、いくつかの注文がより最適な実行不可能な)。いる場合は、すべての必要なインポート ライブラリ存在、実行可能ファイル (DLL) ビルドへのリンクを実行します。 これには、インポート ライブラリが生成されます。 それ以外の場合、インポート ライブラリを作成するように LIB を実行します。  
  
     追加のファイルと/DEF オプションを使用して LIB を実行すると、します。EXP の拡張機能です。 します。EXP ファイルは、後で、実行可能ファイルをビルドに使用する必要があります。  
  
2.  すべてのインポート ライブラリをビルドするリンクまたは LIB のいずれかを使用すると、戻り、ビルド前の手順で構築されていないすべての実行可能ファイルへのリンクを実行します。 リンク行に対応する .exp ファイルを指定する必要がありますに注意してください。  
  
     DLL1 用インポート ライブラリを生成するために以前 LIB ユーティリティを実行した場合 LIB がによって生成された DLL1.exp ファイルにもします。 DLL1.dlll を構築するときに、リンクへの入力として DLL1.exp を使用する必要があります。  
  
 次の図は、2 つの相互インポート Dll、DLL1 および DLL2 ソリューションを示します。 手順 1 では、DLL1 で/DEF オプションを設定すると、LIB を実行します。 手順 1 では、DLL1.lib、インポート ライブラリ、および DLL1.exp が生成されます。ステップ 2 で、インポート ライブラリは DLL2 DLL2 のシンボルのインポート ライブラリを生成する順番をビルドに使用されます。 手順 3 では、DLL1.exp と DLL2.lib 入力として使用して、DLL1 を構築します。 LIB DLL2 のインポート ライブラリをビルドに使用されなかったためには、DLL2 の .exp ファイルが必要ないことに注意してください。  
  
 ![相互インポートを使用して 2 つの Dll をリンクする](../build/media/vc37yj1.gif "vc37YJ1")  
相互インポートを使った 2 つの DLL のリンク  
  
## <a name="limitations-of-afxext"></a>_AFXEXT の制限事項  
 使用することができます、 `_AFXEXT` MFC 拡張 Dll が MFC 拡張 Dll の複数のレイヤーがあるない限りのプリプロセッサ シンボル。 MFC 拡張 Dll を呼び出す、または独自の MFC 拡張 Dll で、MFC クラスから派生し、内のクラスから派生するをした場合は、あいまいさを回避するプリプロセッサ シンボルを使用する必要があります。  
  
 問題は、その Win32、として任意のデータを明示的に宣言する必要があります**方式**、DLL からエクスポートする場合と **_declspec (dllimport)** DLL からインポートする場合は、します。 定義するときに`_AFXEXT`、MFC ヘッダーことを確認して**AFX_EXT_CLASS**が正しく定義されています。  
  
 場合などがある複数のレイヤー、1 つの記号**AFX_EXT_CLASS** MFC 拡張 DLL 可能性がある新しいクラスをエクスポートするだけでなく他の MFC 拡張 DLL からの他のクラスをインポートするために十分ではありません。 この問題を解決するには、DLL を使うと、DLL 自体を構築することを示す特別なプリプロセッサ シンボルを使用します。 たとえば、次の 2 つの MFC 拡張 Dll、A.dll および B.dll 想像してください。 それらの各ファイルはエクスポート A.h および B.h、一部のクラスです。 B.dll は、A.dll からクラスを使用します。 ヘッダー ファイルは、次のようになります。  
  
```  
/* A.H */  
#ifdef A_IMPL  
   #define CLASS_DECL_A   __declspec(dllexport)  
#else  
   #define CLASS_DECL_A   __declspec(dllimport)  
#endif  
  
class CLASS_DECL_A CExampleA : public CObject  
{ ... class definition ... };  
  
// B.H  
#ifdef B_IMPL  
   #define CLASS_DECL_B   __declspec(dllexport)  
#else  
   #define CLASS_DECL_B   __declspec(dllimport)  
#endif  
  
class CLASS_DECL_B CExampleB : public CExampleA  
{ ... class definition ... };  
...  
```  
  
 A.dll のビルド時にでビルド`/D A_IMPL`B.dll のビルド時にでビルドおよび`/D B_IMPL`です。 DLL ごとに個別のシンボルを使用して、`CExampleB`はエクスポートと`CExampleA`B.dll を構築するときにインポートします。 `CExampleA` A.dll を構築するときにエクスポートし、B.dll (または他のクライアント) を使用する場合をインポートします。  
  
 組み込みを使用する場合、この種類の重ね順を実行できません**AFX_EXT_CLASS**と`_AFXEXT`プリプロセッサ シンボル。 上記の手法では、その Active テクノロジ、データベース、およびネットワークの MFC 拡張 Dll を作成するときに MFC 自体のメカニズムを使用するいないとは異なりの方法でこの問題は解決します。  
  
## <a name="not-exporting-the-entire-class"></a>クラス全体をエクスポートしません。  
 クラス全体をエクスポートしない場合は、ときに、MFC マクロで作成されたために必要なデータ項目が正しくエクスポートされることを確実にあります。 再定義してこれ行う`AFX_DATA`特定のクラスのマクロにします。 これはクラス全体をエクスポートしない場合はいつでも行う必要があります。  
  
 例えば:  
  
```  
/* A.H */  
#ifdef A_IMPL  
   #define CLASS_DECL_A  _declspec(dllexport)  
#else  
   #define CLASS_DECL_A  _declspec(dllimport)  
#endif  
  
#undef  AFX_DATA  
#define AFX_DATA CLASS_DECL_A  
  
class CExampleA : public CObject  
{  
   DECLARE_DYNAMIC()  
   CLASS_DECL_A int SomeFunction();  
   //... class definition ...  
};  
  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
### <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [DLL からのエクスポートします。](../build/exporting-from-a-dll.md)  
  
-   [使用して、DLL からエクスポートします。DEF ファイル](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [関数を使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS を使ったエクスポート/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 言語の実行可能ファイルで使用するための C++ 関数をエクスポートします。](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [エクスポート方式を使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [_Declspec (dllimport) を使用してアプリケーションをインポートします。](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
### <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [LIB のユーティリティと/DEF オプション](../build/reference/lib-reference.md)  
  
## <a name="see-also"></a>関連項目  
 [インポートとエクスポート](../build/importing-and-exporting.md)