---
title: 正規の MFC Dll が MFC と動的にリンク |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- AFX_MANAGE_STATE macro
- DLLs [C++], regular
- shared DLL versions [C++]
- dynamically linked DLLs [C++]
ms.assetid: b4f7ab92-8723-42a5-890e-214f4e29dcd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e20a3937786d65945256eeadcf0bf08b0314470
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="regular-mfc-dlls-dynamically-linked-to-mfc"></a>MFC と動的にリンクされている標準 MFC Dll
MFC DLL が MFC と動的にリンク、通常は内部的には、MFC を使用する DLL と、MFC または非 MFC の実行可能ファイルによって、DLL からエクスポートされた関数を呼び出すことができます。 名前について説明します、MFC (MFC の共有バージョンとも呼ばれます) のダイナミック リンク ライブラリのバージョンを使ってこの種の DLL がビルドされます。 通常、関数は、通常、標準の C インターフェイスを使用して MFC DLL からエクスポートします。  
  
 追加する必要があります、 `AFX_MANAGE_STATE` MFC DLL のいずれかに現在のモジュール状態を設定すると動的にリンクするレギュラーの MFC Dll でエクスポートされたすべての関数の先頭にします。 これは、DLL からエクスポートされた関数の先頭に次のコード行を追加することによって行います。  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 MFC と動的にリンクされている標準 MFC DLL には、次の機能があります。  
  
-   これは、新しい種類の Visual C 4.0 で導入された DLL です。  
  
-   クライアント実行可能ファイルは、(C、C++、Pascal、Visual Basic、および) などです。 Dll の使用をサポートする任意の言語で記述できます。これは、MFC アプリケーションではありません。  
  
-   静的にリンクされた正規 MFC DLL とは異なりこの種類の DLL は MFC DLL (共有 MFC DLL とも呼ばれます) に動的にリンクします。  
  
-   この種類の DLL にリンクされている MFC インポート ライブラリは、MFC 拡張 Dll または MFC の DLL を使用してアプリケーションに使用されるものと同じ: MFCxx (D) .lib です。  
  
 MFC と動的にリンクされている標準 MFC DLL には、次の要件があります。  
  
-   これらの Dll がコンパイルされる **_AFXDLL** MFC DLL に動的にリンクされている実行可能ファイルと同じように定義されています。 しかし、 **_USRDLL** MFC と静的にリンクされている標準 MFC DLL と同じようにも定義します。  
  
-   この種類の DLL のインスタンスを作成する必要があります、 `CWinApp`-クラスを派生します。  
  
-   この種類の DLL は、 `DllMain` MFC によって提供されます。 内のすべての DLL に固有の初期化コードを配置、`InitInstance`でメンバー関数と終了コード`ExitInstance`標準 MFC アプリケーションと同様です。  
  
 この種の DLL は、MFC のダイナミック リンク ライブラリ バージョンを使用するため、DLL のいずれかに現在のモジュール状態を明示的に設定する必要があります。 これを行うを使用して、 [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) DLL からエクスポートされたすべての関数の先頭にします。  
  
 標準の MFC Dll が必要、`CWinApp`の MFC アプリケーションのように、クラスとそのアプリケーション クラスの 1 つのオブジェクトを派生します。 ただし、 `CWinApp` DLL のオブジェクトには、メイン メッセージ ポンプがない、`CWinApp`アプリケーションのオブジェクト。  
  
 なお、 `CWinApp::Run` DLL には、アプリケーションは、メイン メッセージ ポンプを所有しているためのメカニズムは適用されません。 アプリケーションのメイン メッセージ ポンプが呼び出される DLL エクスポートのルーチンを呼び出す必要があります、DLL は、モードレス ダイアログ ボックスが表示または、独自のメイン フレーム ウィンドウ、`CWinApp::PreTranslateMessage`です。  
  
 すべての DLL に固有の初期化を配置、`CWinApp::InitInstance`メンバー関数は、通常の MFC アプリケーションと同様にします。 `CWinApp::ExitInstance`のメンバー関数、`CWinApp`派生クラスが提供される MFC から呼び出される`DllMain`DLL が読み込まれる前に機能します。  
  
 アプリケーションを使用して、共有 Dll MFCx0.dll Msvcr*0.dll (または同様のファイル) を配布する必要があります。  
  
 MFC と動的にリンクされている DLL は、MFC に静的にリンクできません。 標準の MFC Dll へのリンクをアプリケーションに動的にリンク MFC、その他の DLL と同じようにします。  
  
 通常、シンボルは、通常、標準の C インターフェイスを使用して MFC DLL からエクスポートされます。 正規の MFC DLL からエクスポートされた関数の宣言では、次のようになります。  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 正規の MFC DLL 内のすべてのメモリ割り当てが DLL 内で維持する必要があります。DLL またはしないでくださいに渡す受信呼び出しの実行可能ファイルから、次のいずれか。  
  
-   MFC オブジェクトへのポインター  
  
-   MFC によって割り当てられたメモリへのポインター  
  
 上記のいずれかにする場合、または呼び出しの実行可能ファイルと、DLL の間で MFC の派生オブジェクトを渡す必要がある場合は、MFC 拡張 DLL をビルドする必要があります。  
  
 データのコピーを作成する場合にのみ、C ランタイム ライブラリによって、アプリケーションと DLL の間でポインターを割り当てられたメモリに渡すも安全です。 必要がありますいないを削除またはこれらのポインターのサイズを変更するか、または使用メモリのコピーを作成せずします。  
  
 MFC とリンクするレギュラー DLL をビルド MFC を動的に、ときにマクロを使用する必要があります。 [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) MFC モジュール状態を正しく切り替える。 これは、DLL からエクスポートされた関数の先頭に次のコード行を追加することによって行います。  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 **AFX_MANAGE_STATE**正規の MFC dll に静的にリンクする MFC または MFC 拡張 Dll で、マクロは使用できません。 詳細については、次を参照してください。 [MFC モジュールの状態データを管理する](../mfc/managing-the-state-data-of-mfc-modules.md)です。  
  
 作成、ビルド、および標準 MFC DLL を使用する方法の例は、サンプルを参照してください。[は](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap)します。 MFC と動的にリンクする標準の MFC Dll の詳細については、サンプルの抽象で"への変換を動的にリンクを MFC DLL"というタイトルのセクションを参照してください。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [正規の MFC Dll を初期化します。](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [正規の MFC DLL のモジュールの状態は、MFC と動的にリンク](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
  
-   [MFC モジュールの状態データを管理します。](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [レギュラー MFC DLL でのデータベース、OLE、およびソケット MFC 拡張 DLL の使用](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [DLL の一部としての MFC を使用します。](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
## <a name="see-also"></a>関連項目  
 [DLL の種類](../build/kinds-of-dlls.md)