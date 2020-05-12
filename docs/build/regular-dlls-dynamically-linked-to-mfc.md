---
title: MFC と動的にリンクされる標準 MFC DLL
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- AFX_MANAGE_STATE macro
- DLLs [C++], regular
- shared DLL versions [C++]
- dynamically linked DLLs [C++]
ms.assetid: b4f7ab92-8723-42a5-890e-214f4e29dcd0
ms.openlocfilehash: 3bfed5f75dab4c501708950fdb99f53c40ec142c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315002"
---
# <a name="regular-mfc-dlls-dynamically-linked-to-mfc"></a>MFC と動的にリンクされる標準 MFC DLL

MFC に動的にリンクされる標準 MFC DLL は、MFC を内部で使用する DLL であり、その DLL 内のエクスポートされた関数は、MFC または非 MFC 実行可能ファイルから呼び出すことができます。 名前が示すとおり、この種の DLL は、MFC のダイナミックリンク ライブラリ バージョン (MFC の共有バージョンとも呼ばれます) を使用してビルドされます。 通常、関数は標準の C インターフェイスを使用して標準 MFC DLL からエクスポートされます。

MFC に動的にリンクされる標準 MFC Dll 内のエクスポートされたすべての関数の先頭に `AFX_MANAGE_STATE` マクロを追加して、現在のモジュールの状態を DLL の状態に設定する必要があります。 これを行うには、DLL からエクスポートされた関数の先頭に次のコード行を追加します。

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

MFC に動的にリンクされる標準 MFC DLL には、次の特徴があります。

- これは、Visual C++ 4.0 で導入された新しい種類の DLL です。

- クライアント実行可能ファイルは、DLL (C、C++、Pascal、Visual Basic など) の使用をサポートする任意の言語で記述できます。MFC アプリケーションである必要はありません。

- 静的にリンクされる標準 MFC DLL とは異なり、この種類の DLL は、MFC DLL (共有 MFC DLL とも呼ばれます) に動的にリンクされます。

- この種類の DLL にリンクされる MFC インポート ライブラリは、MFC 拡張 DLL または MFC DLL を使用するアプリケーションに使用されるもの (MFCxx(D).lib) と同じです。

MFC に動的にリンクされる標準 MFC DLL には、次の要件があります。

- MFC DLL に動的にリンクされる実行可能ファイルと同様、これらの DLL も、 **_AFXDLL**を定義してコンパイルされます。 ただし、MFC に静的にリンクされる標準 MFC DLL と同様、 **_USRDLL** も定義されます。

- この種類の DLL は、`CWinApp` 派生クラスをインスタンス化する必要があります。

- この種類の DLL では、MFC から提供される `DllMain` を使用します。 通常の MFC アプリケーションと同様、すべての DLL 固有の初期化コードを `InitInstance` メンバー関数内に配置し、終了コードを `ExitInstance` 内に配置します。

この種類の DLL では、MFC のダイナミックリンク ライブラリ バージョンが使用されるため、現在のモジュールの状態を DLL の状態に明示的に設定する必要があります。 これを行うには、DLL からエクスポートされたすべての関数の先頭に [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) マクロを使用します。

標準 MFC DLL には、MFC アプリケーションと同様に、`CWinApp` 派生クラスと、そのアプリケーション クラスの 1 つのオブジェクトが必要です。 ただし、DLL の `CWinApp` オブジェクトは、アプリケーションの `CWinApp` オブジェクトとは異なり、メイン メッセージ ポンプはありません。

アプリケーションにはメイン メッセージ ポンプがあるため、`CWinApp::Run` メカニズムは DLL に適用されないことに注意してください。 DLL がモードレス ダイアログを開く場合、または独自のメイン フレーム ウィンドウがある場合、アプリケーションのメイン メッセージ ポンプは、DLL によってエクスポートされたルーチンを呼び出し、そのルーチンが `CWinApp::PreTranslateMessage`を呼び出す必要があります。

通常の MFC アプリケーションと同様、すべての DLL 固有の初期化コードを `CWinApp::InitInstance` メンバー関数内に配置します。 `CWinApp` 派生クラスの `CWinApp::ExitInstance` メンバー関数は、DLL がアンロードされる前に、MFC によって提供される `DllMain` 関数から呼び出されます。

アプリケーションと共に、共有 DLL の MFCx0.dll と Msvcr*0.dll (または同様のファイル) を配布する必要があります。

MFC に動的にリンクされた DLL をさらに静的に MFC にリンクすることはできません。 アプリケーションは、他の DLL と同様に、MFC に動的にリンクされた標準 MFC DLL にリンクします。

通常、シンボルは、標準の C インターフェイスを使用して標準 MFC DLL からエクスポートされます。 標準 MFC DLL からエクスポートされた関数の宣言は、次のようになります。

```
extern "C" __declspec(dllexport) MyExportedFunction( );
```

標準 MFC DLL 内のメモリ割り当てはすべて、その DLL 内に存在する必要があります。つまり、DLL は、呼び出し実行可能ファイルとの間で次のいずれかのポインターを受け渡しすることはできません。

- MFC オブジェクトへのポインター

- MFC によって割り当てられたメモリへのポインター

上記のいずれかを受け渡す必要がある場合、または呼び出し元の実行可能ファイルと DLL との間で MFC 派生オブジェクトを受け渡す必要がある場合は、MFC 拡張 DLL をビルドする必要があります。

データのコピーを作成する場合のみ、C ランタイム ライブラリによって割り当てられたメモリへのポインターをアプリケーションと DLL の間で安全に受け渡すことができます。 これらのポインターを削除またはサイズ変更することはできません。また、メモリのコピーを作成せずに使用することもできません。

MFC に動的にリンクする標準 MFC DLL をビルドする場合、[AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) マクロを使用して MFC モジュールの状態を正しく切り替える必要があります。 これを行うには、DLL からエクスポートされた関数の先頭に次のコード行を追加します。

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

MFC に静的にリンクする MFC DLL 内、または MFC 拡張 DLL 内で **AFX_MANAGE_STATE** マクロを使用することはできません。 詳細については、「[MFC モジュールの状態データの管理](../mfc/managing-the-state-data-of-mfc-modules.md)」を参照してください。

標準 MFC DLL を記述、ビルド、使用する方法の例については、サンプルの [DLLScreenCap](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap) を参照してください。 MFC に動的にリンクする標準 MFC DLL の詳細については、サンプルの要約にある「Converting DLLScreenCap to Dynamically Link with the MFC DLL」 (MFC DLL に動的にリンクするための DLLScreenCap の変換) というタイトルのセクションを参照してください。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [標準 MFC DLL の初期化](run-time-library-behavior.md#initializing-regular-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [MFC と動的にリンクされているレギュラー MFC DLL のモジュール状態](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)

- [MFC モジュールの状態データの管理](../mfc/managing-the-state-data-of-mfc-modules.md)

- [レギュラー MFC DLL でのデータベース、OLE、およびソケット MFC 拡張 DLL の使用](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [DLL の構成要素としての MFC](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

## <a name="see-also"></a>関連項目

[DLL の種類](kinds-of-dlls.md)
