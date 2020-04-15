---
title: 'テクニカル ノート 11: DLL の構成要素としての MFC'
ms.date: 11/04/2016
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
ms.openlocfilehash: 0f4d4e2ed76a0fa5f8f775345fc672a1df055a39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370438"
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>テクニカル ノート 11: DLL の構成要素としての MFC

このノートでは、MFC ライブラリを Windows ダイナミック リンク ライブラリ (DLL) の一部として使用できる、通常の MFC DLL について説明します。 Windows DLL と、そのビルド方法に精通していることを前提としています。 MFC ライブラリの拡張機能を作成できる MFC 拡張 DLL の詳細については[、「MFC の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)」を参照してください。

## <a name="dll-interfaces"></a>DLL インターフェイス

通常の MFC DLL は、アプリケーションと DLL の間のインターフェイスが C 型の関数または明示的にエクスポートされたクラスで指定されていることを前提としています。 MFC クラス インターフェイスをエクスポートできません。

DLL とアプリケーションの両方で MFC を使用する場合は、両方の方法で MFC ライブラリの共有バージョンを使用するか、ライブラリのコピーに静的にリンクするかを選択できます。 アプリケーションと DLL は、どちらも MFC ライブラリの標準バージョンのいずれかを使用できます。

通常の MFC DLL には、次のような利点があります。

- DLL を使用するアプリケーションは、MFC を使用する必要はありません。

- MFC に静的にリンクする標準 MFC DLL では、DLL のサイズは、使用およびリンクされている MFC および C ランタイム ルーチンにのみ依存します。

- MFC に動的にリンクする通常の MFC DLL を使用すると、共有バージョンの MFC を使用するメモリの節約が大幅に行われる可能性があります。 ただし、\<共有 DLL、Mfc*バージョン*>.dll、および Msvvcrt\<*バージョン*>.dll を DLL と共に配布する必要があります。

- DLL の設計は、クラスの実装方法とは無関係です。 DLL 設計では、必要な API にのみエクスポートされます。 その結果、実装が変更された場合でも、通常の MFC DLL は有効です。

- MFC に静的にリンクする通常の MFC DLL では、DLL とアプリケーションの両方が MFC を使用する場合、アプリケーションで DLL とは異なるバージョンの MFC を使用する場合、またはその逆のバージョンに問題はありません。 MFC ライブラリは各 DLL または EXE に静的にリンクされているため、どのバージョンを使用しているかは問いません。

## <a name="api-limitations"></a>API の制限事項

MFC の機能の中には、技術的な制限や、通常はアプリケーションが提供するサービスが原因で、DLL のバージョンに適用されないものがあります。 現在のバージョンの MFC では、適用できない関数は`CWinApp::SetDialogBkColor`.

## <a name="building-your-dll"></a>DLL のビルド

MFC に静的にリンクする標準 MFC DLL をコンパイルする`_USRDLL`場合`_WINDLL`は、シンボルを定義する必要があります。 DLL コードは、次のコンパイラ スイッチを使用してコンパイルする必要もあります。

- **/D_WINDLL**は、コンパイルが DLL 用であることを示します。

- **/D_USRDLL**は、通常の MFC DLL をビルドしていることを指定します

これらのシンボルを定義し、MFC に動的にリンクする通常の MFC DLL をコンパイルするときに、これらのコンパイラ スイッチを使用する必要もあります。 さらに、シンボル`_AFXDLL`を定義し、DLL コードを次のようにコンパイルする必要があります。

- **/D_AFXDLL** MFC に動的にリンクする通常の MFC DLL をビルドすることを指定します。

アプリケーションと DLL 間のインターフェイス (API) は、明示的にエクスポートする必要があります。 インターフェイスを低帯域幅に定義し、可能であれば C インターフェイスのみを使用することをお勧めします。 直接 C インターフェイスは、複雑な C++ クラスよりも保守が容易です。

Api は、C ファイルと C++ ファイルの両方で含めることができる個別のヘッダーに配置します。 例については、MFC の高度な概念サンプル[DLLScreenCap](../overview/visual-cpp-samples.md)のヘッダー ScreenCap.h を参照してください。 関数をエクスポートするには、`EXPORTS`モジュール定義ファイル (.DEF) または`__declspec(dllexport)`関数定義に含める。 これらの`__declspec(dllimport)`関数をクライアント実行可能ファイルにインポートするために使用します。

MFC に動的にリンクする通常の MFC DLL では、エクスポートされたすべての関数の先頭にAFX_MANAGE_STATE マクロを追加する必要があります。 このマクロは、DLL の現在のモジュールの状態を設定します。 このマクロを使用するには、DLL からエクスポートされた関数の先頭に次のコード行を追加します。

`AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`

## <a name="winmain---dllmain"></a>ウィンメイン -> DllMain

MFC ライブラリは、標準的な MFC`DllMain`アプリケーションのように[CWinApp](../mfc/reference/cwinapp-class.md)派生オブジェクトを初期化する標準 Win32 エントリ ポイントを定義します。 一般的な MFC アプリケーションと同様に、すべての DLL 固有の初期化を[InitInstance](../mfc/reference/cwinapp-class.md#initinstance)メソッドに配置します。

[CWinApp::Run](../mfc/reference/cwinapp-class.md#run)メカニズムは、アプリケーションがメイン メッセージ ポンプを所有しているため、DLL には適用されないことに注意してください。 DLL がモードレス ダイアログを表示する場合、または独自のメイン フレーム ウィンドウがある場合、アプリケーションのメイン メッセージ ポンプは[:P、Dll](../mfc/reference/cwinapp-class.md#pretranslatemessage)エクスポートされたルーチンを呼び出す必要があります。

この関数の使用については、DLLScreenCap サンプルを参照してください。

MFC`DllMain`が提供する関数は、DLL がアンロードされる`CWinApp`前に派生したクラスの[CWinApp::ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance)メソッドを呼び出します。

## <a name="linking-your-dll"></a>DLL のリンク

MFC に静的にリンクする通常の MFC DLL では、DLL を Nafxcwd.lib または Nafxcw.lib とリンクし、Libcmt.lib という名前の C ランタイムのバージョンとリンクする必要があります。 これらのライブラリはあらかじめビルドされており、Visual C++ セットアップを実行するときに指定することによってインストールできます。

## <a name="sample-code"></a>サンプル コード

完全なサンプルについては、MFC の詳細概念サンプル プログラム DLLScreenCap を参照してください。 このサンプルで注目すべき点は、次のとおりです。

- DLL のコンパイラ フラグとアプリケーションのコンパイラ フラグが異なります。

- リンク行と .DLL の DEF ファイルとアプリケーション用の DEF ファイルは異なります。

- DLL を使用するアプリケーションは、C++ で使用する必要はありません。

- アプリケーションと DLL の間のインターフェイスは、C または C++ で使用できる API であり、DLLScreenCap.def でエクスポートされます。

MFC に静的にリンクする通常の MFC DLL で定義されている API の例を次に示します。 この例では、宣言は C++`extern "C" { }`ユーザーのブロックで囲まれています。 これにはいくつかの利点があります。 最初に、非 C++ クライアント アプリケーションで DLL API を使用できるようにします。 第 2 に、C++ 名のマングリングはエクスポートされた名前に適用されないため、DLL のオーバーヘッドが削減されます。 最後に、 に明示的に追加する方が簡単になります。DEF ファイル (序数でエクスポート) を使用せずに名前のマングリングを気にする必要はありません。

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

API で使用される構造体は、MFC クラスから派生しておらず、API ヘッダーで定義されます。 これにより、DLL とアプリケーション間のインターフェイスの複雑さが軽減され、C プログラムで DLL を使用できるようになります。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
