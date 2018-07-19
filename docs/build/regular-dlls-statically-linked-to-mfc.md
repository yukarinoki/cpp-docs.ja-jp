---
title: MFC と静的にリンクされている標準 MFC Dll |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- regular MFC DLLs [C++]
- DLLs [C++], regular
- USRDLLs
- USRDLLs, statically linked to MFC
- statically linked DLLs [C++]
- regular MFC DLLs [C++], statically linked to MFC
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c48fdfb0b10541c1643ec49038e29cfa60c633d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383749"
---
# <a name="regular-mfc-dlls-statically-linked-to-mfc"></a>MFC と静的にリンクされている標準 MFC Dll
MFC DLL が MFC と静的にリンク、通常は内部的には、MFC を使用する DLL と、MFC または非 MFC の実行可能ファイルによって、DLL からエクスポートされた関数を呼び出すことができます。 名前が示すようこの種の DLL は MFC のスタティック リンク ライブラリ バージョンを使用して構築します。 通常、関数は、通常、標準の C インターフェイスを使用して MFC DLL からエクスポートします。 作成、ビルド、および標準 MFC DLL を使用する方法の例は、サンプルを参照してください。[は](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap)します。  
  
 USRDLL という用語は、Visual C のドキュメントでは使用されなくに注意してください。 MFC と静的にリンクされている標準 MFC DLL は、これまでの USRDLL と同じ特性を持ちます。  
  
 MFC と静的にリンクされるレギュラー MFC DLL には、次の機能があります。  
  
-   クライアント実行可能ファイルは、(C、C++、Pascal、Visual Basic、および) などです。 Dll の使用をサポートする任意の言語で記述できます。これは、MFC アプリケーションではありません。  
  
-   DLL は、アプリケーションで使用される同じ MFC スタティック リンク ライブラリにリンクできます。 Dll は、スタティック リンク ライブラリの別のバージョンではなくなりました。  
  
-   MFC のバージョン 4.0 より前に、は、として、Usrdll には、同じ種類の MFC と静的にリンクされている標準の MFC Dll と機能が用意されています。 Visual C の時点でバージョン 4.0 では、用語の USRDLL は今後使用しません。  
  
 MFC と静的にリンクされるレギュラー MFC DLL には、次の要件があります。  
  
-   この種類の DLL から派生したクラスのインスタンスを作成する必要があります`CWinApp`です。  
  
-   この種類の DLL は、 `DllMain` MFC によって提供されます。 内のすべての DLL に固有の初期化コードを配置、`InitInstance`でメンバー関数と終了コード`ExitInstance`標準 MFC アプリケーションと同様です。  
  
-   まだを定義する必要がありますがという用語は、USRDLL は今後使用しませんが、"**_USRDLL**"コンパイラのコマンドラインでします。 この定義は、宣言が MFC ヘッダー ファイルからプルされたを決定します。  
  
 標準の MFC Dll が必要、`CWinApp`の MFC アプリケーションのように、クラスとそのアプリケーション クラスの 1 つのオブジェクトを派生します。 ただし、 `CWinApp` DLL のオブジェクトには、メイン メッセージ ポンプがない、`CWinApp`アプリケーションのオブジェクト。  
  
 なお、 `CWinApp::Run` DLL には、アプリケーションは、メイン メッセージ ポンプを所有しているためのメカニズムは適用されません。 DLL は、モードレス ダイアログを開くか、独自のメイン フレーム ウィンドウする場合、アプリケーションのメイン メッセージ ポンプは、さらに、DLL によってエクスポートされたルーチンを呼び出す必要があります、 `CWinApp::PreTranslateMessage` DLL のアプリケーション オブジェクトのメンバー関数。  
  
 この関数の例はサンプルを参照してください。  
  
 通常、シンボルは、通常、標準の C インターフェイスを使用して MFC DLL からエクスポートされます。 正規の MFC DLL からエクスポートされた関数の宣言は、次のようになります。  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 正規の MFC DLL 内のすべてのメモリ割り当てが DLL 内で維持する必要があります。DLL またはしないでくださいに渡す受信呼び出しの実行可能ファイルから、次のいずれか。  
  
-   MFC オブジェクトへのポインター  
  
-   MFC によって割り当てられたメモリへのポインター  
  
 上記のいずれかの操作または呼び出し元の実行可能ファイルと、DLL の間で MFC の派生オブジェクトを渡す必要がある必要がある場合は、MFC 拡張 DLL をビルドする必要があります。  
  
 データのコピーを作成する場合にのみ、C ランタイム ライブラリによって、アプリケーションと DLL の間でポインターを割り当てられたメモリに渡すも安全です。 必要がありますいないを削除またはこれらのポインターのサイズを変更するか、または使用メモリのコピーを作成せずします。  
  
 MFC と静的にリンクされている DLL は、共有 MFC Dll に動的にリンクできません。 MFC と静的にリンクされる DLL とその他の DLL と同じようにアプリケーションを動的に連結します。アプリケーションは、その他の DLL と同じようにしてリンクします。  
  
 標準の MFC スタティック リンク ライブラリがで説明されている規則に従って名前付き[MFC Dll の名前付け規則](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)です。 ただし、MFC バージョン 3.0 以降では、これが不要でリンクする MFC ライブラリのバージョンをリンカーに手動で指定する必要です。 代わりに、MFC ヘッダー ファイルを自動的に決定に基づいてプリプロセッサでリンクする MFC ライブラリの正しいバージョンを定義するように**\_デバッグ**または **_UNICODE**です。 MFC ヘッダー ファイルでは、MFC ライブラリの特定のバージョンのリンクをリンカーに指示/DEFAULTLIB ディレクティブを追加します。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [正規の MFC Dll を初期化します。](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [DLL の一部としての MFC を使用します。](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [レギュラー MFC DLL でのデータベース、OLE、およびソケット MFC 拡張 DLL の使用](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [MFC DLL を作成します。](../mfc/reference/mfc-dll-wizard.md)  
  
-   [MFC と動的にリンクされるレギュラー MFC DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC 拡張 DLL](../build/extension-dlls-overview.md)  
  
## <a name="see-also"></a>関連項目  
 [DLL の種類](../build/kinds-of-dlls.md)