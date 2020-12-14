---
description: '詳細については、次を参照してください: テクニカルノート 11: MFC を DLL の一部として使用する'
title: 'テクニカル ノート 11: DLL の構成要素としての MFC'
ms.date: 11/04/2016
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
ms.openlocfilehash: 11b50ce361fc9e41c48931daa6bffd30a8c9673e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216029"
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>テクニカル ノート 11: DLL の構成要素としての MFC

このメモでは、MFC ライブラリを Windows ダイナミックリンクライブラリ (DLL) の一部として使用できるようにする通常の MFC Dll について説明します。 Windows Dll とその構築方法について理解していることを前提としています。 Mfc ライブラリの拡張機能を作成するために使用できる MFC 拡張 Dll の詳細については、「 [mfc の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)」を参照してください。

## <a name="dll-interfaces"></a>DLL インターフェイス

通常の MFC Dll では、アプリケーションと DLL の間のインターフェイスが C と同様の関数または明示的にエクスポートされたクラスで指定されていることを想定しています。 MFC クラスインターフェイスはエクスポートできません。

DLL とアプリケーションの両方で MFC を使用する場合は、MFC ライブラリの共有バージョンを使用するか、ライブラリのコピーに静的にリンクするかのどちらかを選択できます。 アプリケーションと DLL はどちらも、MFC ライブラリの標準バージョンのいずれかを使用できます。

通常の MFC Dll には、いくつかの利点があります。

- DLL を使用するアプリケーションは、MFC を使用する必要がなく、Visual C++ アプリケーションである必要はありません。

- MFC と静的にリンクするレギュラー MFC Dll では、DLL のサイズは、使用およびリンクされている MFC および C ランタイムルーチンにのみ依存します。

- Mfc に動的にリンクするレギュラー MFC Dll を使用すると、MFC の共有バージョンを使用した場合のメモリの節約が重要になる場合があります。 ただし、DLL と共に、Mfc .dll と Msvvcrt の共有 Dll を配布する必要があり \<*version*> \<*version*> ます。

- DLL の設計は、クラスの実装方法とは無関係です。 DLL のデザインは、必要な Api にのみエクスポートされます。 その結果、実装が変更された場合でも、通常の MFC Dll は引き続き有効になります。

- MFC に静的にリンクするレギュラー MFC Dll では、DLL とアプリケーションの両方で MFC を使用している場合、DLL とは異なるバージョンの MFC を必要とするアプリケーションに問題はありません。その逆も同様です。 MFC ライブラリは各 DLL または EXE に静的にリンクされているため、どのバージョンがあるかについての質問はありません。

## <a name="api-limitations"></a>API の制限事項

MFC の機能の中には、DLL のバージョンには適用されないものもあります。これは、技術的な制限や、これらのサービスは通常、アプリケーションによって提供されるためです。 現在のバージョンの MFC では、適用できない唯一の関数は `CWinApp::SetDialogBkColor` です。

## <a name="building-your-dll"></a>DLL のビルド

MFC に静的にリンクするレギュラー MFC Dll をコンパイルする場合は、シンボル `_USRDLL` とが `_WINDLL` 定義されている必要があります。 DLL コードは、次のコンパイラスイッチを使用してコンパイルする必要もあります。

- **/D_WINDLL** は、DLL のコンパイルであることを示します。

- **/D_USRDLL** は、通常の MFC DLL をビルドすることを指定します。

また、これらのシンボルを定義し、MFC に動的にリンクするレギュラー MFC Dll をコンパイルするときに、これらのコンパイラスイッチを使用する必要があります。 さらに、シンボルを `_AFXDLL` 定義し、DLL コードをでコンパイルする必要があります。

- **/D_AFXDLL** mfc と動的にリンクするレギュラー mfc DLL をビルドすることを指定します。

アプリケーションと DLL の間のインターフェイス (Api) を明示的にエクスポートする必要があります。 インターフェイスを低帯域幅に定義し、可能であれば C インターフェイスのみを使用することをお勧めします。 ダイレクト C インターフェイスは、より複雑な C++ クラスよりも保守が簡単です。

Api は、C と C++ の両方のファイルに含めることができる別のヘッダーに配置します。 例については、MFC の高度な概念のサンプル [DLLScreenCap](../overview/visual-cpp-samples.md) のヘッダースクリーンショットを参照してください。 関数をエクスポートするには、 `EXPORTS` モジュール定義ファイル () のセクションに関数を入力します。DEF) または `__declspec(dllexport)` を関数定義に含めます。 `__declspec(dllimport)`これらの関数をクライアント実行可能ファイルにインポートするには、を使用します。

MFC に動的にリンクするレギュラー MFC Dll のエクスポートされたすべての関数の先頭に、AFX_MANAGE_STATE マクロを追加する必要があります。 このマクロは、現在のモジュールの状態を DLL の状態に設定します。 このマクロを使用するには、DLL からエクスポートされた関数の先頭に次のコード行を追加します。

`AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`

## <a name="winmain---dllmain"></a>WinMain-> DllMain

MFC ライブラリは、 `DllMain` 一般的な mfc アプリケーションのように、 [CWinApp](../mfc/reference/cwinapp-class.md) の派生オブジェクトを初期化する標準の Win32 エントリポイントを定義します。 通常の MFC アプリケーションのように、すべての DLL 固有の初期化を [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) メソッドに配置します。

アプリケーションはメインメッセージポンプを所有しているため、 [CWinApp:: Run](../mfc/reference/cwinapp-class.md#run) 機構は DLL には適用されません。 DLL でモードレスダイアログが表示される場合、または独自のメインフレームウィンドウがある場合は、アプリケーションのメインメッセージポンプが、 [CWinApp::P retranslatemessage](../mfc/reference/cwinapp-class.md#pretranslatemessage)を呼び出す DLL エクスポートルーチンを呼び出す必要があります。

この関数を使用する場合は、DLLScreenCap サンプルを参照してください。

`DllMain`MFC が提供する関数は、DLL がアンロードされる前に、から派生したクラスの[CWinApp:: exitinstance](../mfc/reference/cwinapp-class.md#exitinstance)メソッドを呼び出し `CWinApp` ます。

## <a name="linking-your-dll"></a>DLL のリンク

MFC に静的にリンクするレギュラー MFC Dll を使用して、DLL を Nafxcwd.lib」または Nafxcw に、Libcmt.lib という名前の C ランタイムのバージョンにリンクする必要があります。 これらのライブラリはあらかじめ構築されており、Visual C++ セットアップを実行するときに指定することでインストールできます。

## <a name="sample-code"></a>サンプル コード

完全なサンプルについては、MFC の高度な概念サンプルプログラム DLLScreenCap を参照してください。 このサンプルで注目すべきいくつかの興味深い点は次のとおりです。

- DLL とアプリケーションのコンパイラフラグが異なります。

- リンクの線と。DLL の DEF ファイルとアプリケーションの DEF ファイルは異なります。

- DLL を使用するアプリケーションは、C++ に存在する必要はありません。

- アプリケーションと DLL の間のインターフェイスは、C または C++ で使用できる API であり、DLLScreenCap を使用してエクスポートされます。

次の例は、MFC と静的にリンクする通常の MFC DLL で定義されている API を示しています。 この例では、宣言は C++ ユーザーのブロックで囲まれてい `extern "C" { }` ます。 これにはいくつかの利点があります。 まず、C + + 以外のクライアントアプリケーションで DLL Api を使用できるようにします。 次に、C++ の名前のマングルがエクスポートされた名前に適用されないため、DLL のオーバーヘッドが軽減されます。 最後に、に明示的に追加することが簡単になります。(序数でエクスポートするための) DEF ファイル。名前の変形について心配する必要はありません。

```cpp
#ifdef __cplusplus
extern "C" {
#endif  /* __cplusplus */

struct TracerData
{
    BOOL bEnabled;
    UINT flags;
};

BOOL PromptTraceFlags(TracerData FAR* lpData);

#ifdef __cplusplus
}
#endif
```

API で使用される構造体は、MFC クラスから派生したものではなく、API ヘッダーで定義されています。 これにより、DLL とアプリケーションの間のインターフェイスの複雑さが軽減され、DLL を C プログラムで使用できるようになります。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
