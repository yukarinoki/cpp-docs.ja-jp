---
description: '詳細情報: 相互インポート'
title: 相互インポート
ms.date: 11/04/2016
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
ms.openlocfilehash: 0015dfe69237ff46ecfbef9ee1f1649fcb04d689
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187495"
---
# <a name="mutual-imports"></a>相互インポート

別の実行可能ファイルへのエクスポートまたはインポートは、インポートが相互 (または循環) である場合に複雑になります。 たとえば、相互に再帰的な関数と同様に、相互にシンボルをインポートする 2 つの DLL があるとします。

実行可能ファイル (通常は DLL) を相互にインポートする場合の問題は、いずれも、ビルドするにはもう一方が先にビルドされている必要があることです。 各ビルド プロセスには、入力として、他のビルド プロセスによって生成されたインポート ライブラリが必要です。

これを解決するには、/DEF オプションを指定して LIB ユーティリティを使用することです。こうすることで、実行可能ファイルをビルドせずにインポート ライブラリを生成できます。 このユーティリティを使用すると、DLL の数や依存関係の複雑さに関係なく、必要なすべてのインポート ライブラリをビルドできます。

相互インポートを処理するための一般的な解決策は次のとおりです。

1. 各 DLL を順番に実行します (順序は任意ですが、より適した順序もあります)。必要なインポート ライブラリがすべて存在し、最新である場合は、LINK を実行して実行可能ファイル (DLL) をビルドします。 これにより、インポート ライブラリが生成されます。 それ以外の場合は、LIB を実行してインポート ライブラリを生成します。

   /DEF オプションを指定して LIB を実行すると、拡張子が .EXP の追加ファイルが作成されます。 実行可能ファイルをビルドするために後で .EXP ファイルを使用する必要があります。

1. LINK または LIB のいずれかを使用してすべてのインポート ライブラリをビルドしたら、戻って LINK を実行し、前の手順でビルドされなかった実行可能ファイルをビルドします。 LINK 行で対応する .exp ファイルを指定する必要があることに注意してください。

   以前に LIB ユーティリティを実行して DLL1 のインポート ライブラリを作成した場合、LIB によって DLL1.exp ファイルも生成されています。 DLL1.dll をビルドするときは、LINK への入力として DLL1.exp を使用する必要があります。

次の図は、2 つの相互インポート DLL (DLL1 と DLL2) の解決策を示しています。 手順 1 では、DLL1 で、/DEF オプションを指定して LIB を実行します。 手順 1 の結果、DLL1.lib、インポート ライブラリ、および DLL1.exp が生成されます。手順 2 では、インポート ライブラリを使用して DLL2 をビルドします。その結果、DLL2 のシンボルのインポート ライブラリが生成されます。 手順 3 では、DLL1.exp および DLL2.lib を入力として使用して DLL1 をビルドします。 DLL2 のインポート ライブラリのビルドには LIB が使用されなかったため、DLL2 の .exp ファイルは必要ありません。

![相互インポートを使って 2 つの DLL をリンクする](media/vc37yj1.gif "相互インポートを使って 2 つの DLL をリンクする")<br/>
相互インポートを使った 2 つの DLL のリンク

## <a name="limitations-of-_afxext"></a>_AFXEXT の制限事項

MFC 拡張 DLL の複数のレイヤーがない限り、`_AFXEXT` プリプロセッサ シンボルを MFC 拡張 DLL に使用できます。 MFC クラスから派生する独自の MFC 拡張 DLL のクラスがあり、そこから呼び出すか派生する MFC 拡張 DLL がある場合は、あいまいさを避けるために独自のプリプロセッサ シンボルを使用する必要があります。

問題は、Win32 では、DLL からエクスポートする場合は **`__declspec(dllexport)`** として、DLL からインポートする場合は **`__declspec(dllimport)`** として明示的にデータを宣言する必要があることです。 `_AFXEXT` を定義するとき、MFC ヘッダーに **AFX_EXT_CLASS** が正しく定義されていることを確認します。

複数のレイヤーがある場合、MFC 拡張 DLL によって別の MFC 拡張 DLL から他のクラスがインポートされるだけでなく、新しいクラスがエクスポートされる可能性があるため、**AFX_EXT_CLASS** などの 1 つのシンボルでは不十分です。 この問題を解決するには、DLL を使用するのではなく、DLL 自体をビルドしていることを示す特別なプリプロセッサ シンボルを使用します。 たとえば、A.dll と B.dll という 2 つの MFC 拡張 DLL があるとします。 それぞれによって、A.h と B.h のいくつかのクラスがエクスポートされます。 B.dll には A.dll のクラスが使用されます。 ヘッダー ファイルは次のようになります。

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

A.dll がビルドされるときは `/D A_IMPL` を使用してビルドされ、B.dll がビルドされるときは `/D B_IMPL` を使用してビルドされます。 DLL ごとに個別のシンボルを使用することにより、B.dll のビルド時に `CExampleB` がエクスポートされ、`CExampleA` がインポートされます。 `CExampleA` は、A.dll のビルド時にエクスポートされ、B.dll (または他のクライアント) から使用されるときにはインポートされます。

組み込みの **AFX_EXT_CLASS** および `_AFXEXT` プリプロセッサ シンボルを使用する場合、この種類のレイヤー化は実行できません。 上記の手法では、アクティブなテクノロジ、データベース、およびネットワーク MFC 拡張 DLL を構築するときに MFC 自体に使用されるメカニズムとは異なる方法でこの問題を解決します。

## <a name="not-exporting-the-entire-class"></a>クラス全体をエクスポートしない

クラス全体をエクスポートしない場合は、MFC マクロによって作成された必要なデータ項目が正しくエクスポートされるようにする必要があります。 そのためには、`AFX_DATA` を特定のクラスのマクロに再定義します。 クラス全体をエクスポートしない場合は、この処理を常に実行することをお勧めします。

次に例を示します。

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

- [DLL からエクスポートする](exporting-from-a-dll.md)

- [.DEF ファイルを使用して DLL からエクスポートする](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) を使用して DLL からエクスポートする](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS を使用してエクスポートとインポートを行う](exporting-and-importing-using-afx-ext-class.md)

- [C 言語の実行可能ファイルで使用する C++ 関数をエクスポートする](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [エクスポート方式を使い分ける](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

### <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [LIB ユーティリティと /DEF オプション](reference/lib-reference.md)

## <a name="see-also"></a>関連項目

[インポートとエクスポート](importing-and-exporting.md)
