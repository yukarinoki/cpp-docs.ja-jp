---
title: 拡張 DLL
ms.date: 05/06/2019
helpviewer_keywords:
- memory [C++], DLLs
- MFC extension DLLs [C++]
- AFXDLL library
- shared resources [C++]
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- resource sharing [C++]
- extension DLLs [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: f69ac3d4-e474-4b1c-87a1-6738843a135c
ms.openlocfilehash: 55b1e55a9c7bdf6daaff98a7fe3f1a2a55f68334
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220766"
---
# <a name="mfc-extension-dlls"></a>MFC 拡張 DLL

MFC 拡張 DLL は、既存の MFC ライブラリ クラスから派生した再利用可能なクラスを主に実装する DLL です。

MFC 拡張 DLL の特長と必要条件は、以下のとおりです。

- クライアント実行可能ファイルは、`_AFXDLL` が定義されコンパイルされた MFC アプリケーションである必要があります。

- MFC 拡張 DLL は、MFC と動的にリンクされている標準 MFC DLL で使用することもできます。

- MFC 拡張 DLL は、`_AFXEXT` を定義してコンパイルする必要があります。 この結果、`_AFXDLL` が強制的に定義され、正しい宣言が MFC ヘッダー ファイルから引き出されることが保証されます。 また、DLL のビルド時に `AFX_EXT_CLASS` が `__declspec(dllexport)` として定義されます。この定義は、このマクロを使ってお使いの MFC 拡張 DLL 内のクラスを宣言する場合に必要です。

- MFC 拡張 DLL は、このオブジェクトを提供するために、`CWinApp` の派生クラスをインスタンス化せず、クライアント アプリケーション (または DLL) に依存する必要があります。

- ただし、MFC 拡張 DLL では、`DllMain` 関数を提供し、そこで必要な初期化を行う必要があります。

拡張 DLL は、MFC のダイナミック リンク ライブラリ バージョン (MFC の共有バージョン) を使ってビルドされます。 MFC 拡張 DLL を使用できるのは、MFC の共有バージョンを使ってビルドされた MFC の実行可能ファイル (アプリケーションまたは標準 MFC DLL) のみです。 クライアント アプリケーションおよび MFC 拡張 DLL の両方で、同じバージョンの MFCx0.dll を使用する必要があります。 MFC 拡張 DLL を使うと、MFC から新しいカスタム クラスを派生させ、この拡張バージョンの MFC を、ご自分の DLL を呼び出すアプリケーションに指定できます。

また、拡張 DLL を使うと、アプリケーションと DLL の間で MFC の派生オブジェクトをやり取りすることもできます。 やり取りされるオブジェクトに関連付けられたメンバー関数は、そのオブジェクトが作成されたモジュール内にあります。 これらの関数は MFC の共有 DLL バージョンの使用時に正しくエクスポートされるので、MFC または MFC から派生したオブジェクト ポインターをアプリケーションとそれがお見込む MFC 拡張 DLL 間で自由にやり取りできます。

MFC の拡張 DLL で MFC の共有バージョンを使う方法は、アプリケーションで MFC の共有バージョンを使う方法と同じです。ただし、考慮が必要な点がいくつかあります。

- 拡張 DLL には `CWinApp` 派生オブジェクトがありません。 したがって、クライアント アプリケーションの `CWinApp` 派生オブジェクトを使用する必要があります。 クライアント アプリケーションには、メイン メッセージ ポンプ、アイドル ループなどが備わっています。

- MFC の拡張 DLL は、`AfxInitExtensionModule` 関数内の `DllMain` を呼び出します。 この関数の戻り値をチェックする必要があります。 `AfxInitExtensionModule` から 0 が返されると、`DllMain` 関数から 0 が返されます。

- MFC 拡張 DLL がアプリケーションに `CRuntimeClass` オブジェクトまたはリソースをエクスポートする場合、初期化中に **CDynLinkLibrary** オブジェクトが作成されます。

MFC のバージョン 4.0 以前では、このような特徴を持つ DLL を AFXDLL と呼んでいました。 AFXDLL は、DLL のビルド中に定義された `_AFXDLL` プリプロセッサ シンボルを参照します。

MFC の共有バージョン用のインポート ライブラリの名前は、[MFC DLL の名前付け規則](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)に関するページで説明される名前付け規約に従って付けられます。 Visual Studio には、MFC DLL の事前構築済みのバージョンのほか、お使いのアプリケーションで使用および配布できる MFC ではない DLL もいくつか用意されています。 また、Program Files\Microsoft Visual Studio フォルダーにインストールされている Redist.txt に説明があります。

.def ファイルを使ってエクスポートする場合は、以下のコードをヘッダー ファイルの先頭と末尾に記述します。

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

これらの 4 行があると、お使いのコードが MFC 拡張 DLL 用に正しくコンパイルされていることになります。 この行を追加しなかった場合は、DLL のコンパイルまたはリンクが正常に処理されない場合があります。

MFC または MFC から派生したオブジェクト ポインターを MFC DLL とやり取りする必要がある場合、その DLL は MFC 拡張 DLL である必要があります。 やり取りされるオブジェクトに関連付けられたメンバー関数は、そのオブジェクトが作成されたモジュール内にあります。 これらの関数は MFC の共有 DLL バージョンの使用時に正しくエクスポートされるので、MFC または MFC から派生したオブジェクト ポインターをアプリケーションとそれがお見込む MFC 拡張 DLL 間で自由にやり取りできます。

C++ の名前修飾およびエクスポートの問題のために、MFC 拡張 DLL のエクスポート リストは同じ DLL のデバッグ バージョンとリテール版では異なる場合があります。また、対応するプラットフォームが異なる DLL の間でも異なる場合があります。 リテール版の MFCx0.dll には、約 2,000 のエクスポート エントリ ポイントがあります。また、デバッグ バージョンの MFCx0.dll には、約 3,000 のエクスポート エントリ ポイントがあります。

## <a name="memory-management"></a>メモリ管理

クライアント アプリケーションのアドレス空間に読み込まれる MFCx0.dll やすべての MFC 拡張 DLL は、同じメモリ アロケーター、リソースの読み込み、およびその他の MFC グローバル状態を同じアプリケーション内にあるかのように共有します。 この点が重要になるのは、MFC でない DLL ライブラリや標準の MFC DLL ではこれとまったく逆のことが行われ、各 DLL が独自のメモリ プールから割り当てられるためです。

MFC 拡張 DLL がメモリを割り当てた場合、そのメモリはその他の任意のアプリケーションによって割り当てられたオブジェクトと自由に混在させることができます。 また、MFC と動的にリンクされたアプリケーションにエラーが発生しても、オペレーティング システムの保護機能によって、DLL を共有している他の MFC アプリケーションの整合性が保持されます。

同じように、リソースの読み込み元である現在の実行可能ファイルなど、他のグローバルな MFC の状態も、クライアント アプリケーションとすべての MFC 拡張 DLL の間および MFCx0.dll 自体の間で共有されます。

## <a name="sharing-resources-and-classes"></a>リソースやクラスの共有

リソースのエクスポートには、リソース リストを使います。 各アプリケーションには、**CDynLinkLibrary** オブジェクトの単方向リストが含まれています。 リソースを読み込む標準的な MFC 実装の多くは、リソースを検索するとき、まず現在のリソース モジュール (`AfxGetResourceHandle`) を探します。ここで見つからないときは、**CDynLinkLibrary** オブジェクトのリストを順に探して必要なリストを読み込みます。

リストを検索する場合、多少速度が低下することとリソース ID 範囲の管理が必要なことが欠点です。 いくつかの MFC 拡張 DLL にリンクされるクライアント アプリケーション側で、DLL のインスタンス ハンドルを指定しなくても、DLL が提供する任意のリソースを使用できるという利点もあります。 `AfxFindResourceHandle` は、リソース リストを検索して一致するリソースを見つけるのに使われる API です。 リソースの名前と型を受け取り、最初に一致したリソース ハンドル (または NULL) を返します。

リソース リストを検索せず、特定の場所からリソースを読み込む場合は、`AfxGetResourceHandle` 関数を使って古いハンドルを保存し、`AfxSetResourceHandle` 関数を使って新規ハンドルを設定します。 クライアント アプリケーションに戻る前に、元のリソース ハンドルを必ず復元してください。 メニューを明示的に読み込む例については、[DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk) の MFC のサンプルから Testdll2 .cpp をご確認ください。

MFC の名前を指定して、MFC オブジェクトを動的に作成する場合も同じです。 MFC オブジェクトの逆シリアル化機構を利用するには、`CRuntimeClass` の全オブジェクトを登録する必要があります。この機構では、要求された型の C++ オブジェクトを、以前に格納された型に基づいて動的に作成し、MFC オブジェクトを再構築します。

MFC サンプルの [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk) の場合、このリストは次のようになります。

```
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE
               |                      |
          TESTDLL2.DLL           TESTDLL2.DLL
               |                      |
          TESTDLL1.DLL           TESTDLL1.DLL
               |                      |
           MFCOxxD.DLL                |
               |                      |
           MFCDxxD.DLL                |
               |                      |
            MFCxxD.DLL            MFCxx.DLL
```

ここで *xx* は、バージョン 4.2 を表す 42 などのバージョン番号です。

MFCxx.dll は、通常、リソース リストやクラス リストの最後にあります。 MFCxx.dll には、標準コマンド ID に対応するプロンプト文字列など、すべての標準 MFC リソースが含まれています。 したがって、この DLL をリストの最後に置くと、DLL とクライアント アプリケーションでは標準 MFC リソースの独自のコピーを持つ必要がなくなり、MFCxx.dll 内の共有リソースに依存できるようになります。

すべての DLL のリソース名とクラス名をクライアント アプリケーションの名前空間に結合した場合は、ID や名前を選択するときに注意が必要です。

[DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk) サンプルでは、複数のヘッダー ファイルを使って、共有リソースの名前空間を管理します。

お使いの MFC 拡張 DLL がアプリケーションごとに追加データを保持する必要がある場合は、**CDynLinkLibrary** から新しいクラスを派生させ、`DllMain` 内に作成できます。 DLL では、実行時に現在のアプリケーションの **CDynLinkLibrary** オブジェクト リストから特定の MFC 拡張 DLL 用のオブジェクトを探し出せます。

### <a name="what-do-you-want-to-do"></a>実行する操作

- [MFC 拡張 DLL の初期化](run-time-library-behavior.md#initializing-extension-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [共有リソース ファイルの使用に関するヒント](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)

- [MFC の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)

- [MFC と静的にリンクされる標準 MFC DLL](regular-dlls-statically-linked-to-mfc.md)

- [MFC と動的にリンクされる標準 MFC DLL](regular-dlls-dynamically-linked-to-mfc.md)

- [レギュラー MFC DLL でのデータベース、OLE、およびソケット MFC 拡張 DLL の使用](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
