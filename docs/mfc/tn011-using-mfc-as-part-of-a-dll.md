---
title: 'TN011: DLL の一部としての MFC の使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.dll
dev_langs:
- C++
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0dcaa0aaf903787549cc91ffd19a34aa4aa066bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384711"
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>テクニカル ノート 11: DLL の構成要素としての MFC
ここでは、標準 MFC Dll では、MFC ライブラリを Windows ダイナミック リンク ライブラリ (DLL) の一部として使用することについて説明します。 これは、Windows の Dll およびそれらをビルドする方法を理解するいると仮定します。 MFC 拡張 Dll の概要については、作成するために、MFC ライブラリの拡張機能を参照してください[MFC の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)します。  
  
## <a name="dll-interfaces"></a>DLL インターフェイス  
 標準の MFC Dll は、アプリケーションと DLL の間のインターフェイスは、C のような関数または明示的にエクスポートされたクラスで指定されると仮定します。 MFC クラスのインターフェイスをエクスポートすることはできません。  
  
 DLL とアプリケーションの両方は、MFC を使用する場合、両方がある場合、MFC ライブラリの共有バージョンを使用するか、またはライブラリのコピーへ静的にリンクします。 アプリケーションと DLL 可能性があります両方を使用して標準のバージョンの MFC ライブラリのいずれか。  
  
 標準の MFC Dll には、いくつかの利点があります。  
  
-   DLL を使用するアプリケーションでは、MFC を使用する必要はありませんしする Visual C アプリケーションである必要はありません。  
  
-   静的にリンクする MFC 標準 MFC dll では、DLL のサイズは使用され、リンクされている MFC および C ランタイム ルーチンにのみ依存します。  
  
-   MFC と動的にリンクする標準 MFC Dll では、MFC の共有バージョンを使用するとメモリの節約を重要なことがあります。 ただし、共有 Dll で Mfc を配布する必要があります*\<バージョン >*.dll および Msvvcrt*\<バージョン >*.dll、DLL とします。  
  
-   DLL のデザインは、クラスを実装する方法の依存しません。 DLL 設計は、必要に応じて Api のみをエクスポートします。 その結果、実装では、変更された場合、標準の MFC Dll が現在も有効にします。  
  
-   静的にリンクする MFC では、標準の MFC Dll が別のバージョンの MFC DLL よりも、またはその逆に、アプリケーションに問題がない場合は、DLL とアプリケーションの両方で MFC を使用します。 MFC ライブラリは、各 DLL または EXE に静的にリンクが、ために、どのバージョンがある質問はありません。  
  
## <a name="api-limitations"></a>API の制限事項  
 MFC 機能の一部は、いずれかの技術的な制限のための DLL バージョンには適用されません、それらのサービスは通常、アプリケーションで指定します。 適用されません唯一の関数は、MFC の現在のバージョンに`CWinApp::SetDialogBkColor`です。  
  
## <a name="building-your-dll"></a>DLL のビルド  
 MFC では、シンボルに静的にリンクしている標準の MFC Dll をコンパイルするときに`_USRDLL`と`_WINDLL`定義する必要があります。 DLL のコードは、次のコンパイラ スイッチを使用してコンパイルすることも必要があります。  
  
- **/D_WINDLL**コンパイルである dll を示します  
  
- **/D_USRDLL**正規 MFC DLL をビルドします。  
  
 また、これらのシンボルを定義して、MFC と動的にリンクする標準の MFC Dll をコンパイルするときに、これらのコンパイラ スイッチを使用する必要があります。 さらに、シンボル`_AFXDLL`定義する必要があり、DLL のコードをコンパイルする必要があります。  
  
- **/方法**MFC と動的にリンクされるレギュラー MFC DLL を作成することを指定します  
  
 アプリケーションと DLL の間のインターフェイス (Api) を明示的にエクスポートする必要があります。 低帯域幅である、インターフェイスを定義して場合は、C インターフェイスのみを使用することをお勧めします。 直接的な C インターフェイスより複雑な C++ クラスよりも管理が容易です。  
  
 C および C++ の両方のファイルを含めることができる別のヘッダーには、独自の Api を配置します。 MFC Advanced Concepts サンプルでは、ヘッダー ScreenCap.h を参照してください[は](../visual-cpp-samples.md)例についてはします。 関数をエクスポートするでそれらを入力、`EXPORTS`モジュール定義ファイルのセクション (です。DEF) または含める`__declspec(dllexport)`関数定義します。 使用して`__declspec(dllimport)`クライアント実行可能ファイルにこれらの関数をインポートします。  
  
 追加する必要があります、 `AFX_MANAGE_STATE` MFC と動的にリンクされるレギュラーの MFC Dll でエクスポートされたすべての関数の先頭にします。 このマクロは、現在のモジュール状態を DLL のいずれかに設定します。 このマクロを使用するのには、DLL からエクスポートされた関数の先頭に次のコード行を追加します。  
  
 `AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`  
  
## <a name="winmain---dllmain"></a>WinMain DllMain]-> [します。  
 標準の Win32、MFC ライブラリ定義`DllMain`を初期化するエントリ ポイント、 [CWinApp](../mfc/reference/cwinapp-class.md)一般的な MFC アプリケーションのようにオブジェクトを派生します。 すべての DLL に固有の初期化を配置、 [InitInstance](../mfc/reference/cwinapp-class.md#initinstance)典型的な MFC アプリケーションと同様の方法です。  
  
 なお、 [:run](../mfc/reference/cwinapp-class.md#run) DLL には、アプリケーションは、メイン メッセージ ポンプを所有しているためのメカニズムは適用されません。 アプリケーションのメイン メッセージ ポンプが呼び出される DLL エクスポートのルーチンを呼び出す必要がありますか、DLL モードレス ダイアログ ボックスが表示されますが、独自のメイン フレーム ウィンドウ、 [cwinapp::pretranslatemessage](../mfc/reference/cwinapp-class.md#pretranslatemessage)です。  
  
 この関数を使用するにはサンプルを参照してください。  
  
 `DllMain` MFC が呼び出す関数、[し](../mfc/reference/cwinapp-class.md#exitinstance)から派生したクラスのメソッド`CWinApp`DLL が読み込まれる前にします。  
  
## <a name="linking-your-dll"></a>DLL をリンク  
 静的にリンクする MFC 標準 MFC dll では、「Nafxcwd.lib または Nafxcw.lib Libcmt.lib をという名前の C ランタイムのバージョンおよび DLL にリンクする必要があります。 これらのライブラリは、あらかじめ組み込まれており、Visual C セットアップを実行するときに指定することによってインストールされます。  
  
## <a name="sample-code"></a>サンプル コード  
 プログラムの完全なサンプルについては、MFC Advanced Concepts サンプルを参照してください。 このサンプルで注目すべき興味深い点をいくつかは次のとおりです。  
  
-   アプリケーションの DLL のコンパイラ フラグとは異なります。  
  
-   リンク線とします。DEF ファイルは、DLL と、アプリケーションの場合は異なります。  
  
-   DLL を使用するアプリケーションは、C++ ではありません。  
  
-   アプリケーションと DLL の間のインターフェイスは、DLLScreenCap.def と API は C または C++ で使用され、エクスポートされることです。  
  
 次の例は、標準 MFC と静的にリンクする MFC DLL で定義されている API を示しています。 この例では、宣言で囲まれた、 `extern "C" { }` C++ ユーザーに対するブロックします。 いくつかの利点があります。 最初に、その DLL Api から使用できるよう C++ 以外のクライアント アプリケーション。 次に、C++ 名前マングルが適用されないためエクスポート名には、DLL のオーバーヘッドが減少します。 最後に、それをやすくに明示的に追加します。DEF ファイル (で序数によるエクスポート) 名前マングルについて心配する必要はありません。  
  
```  
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
  
 API で使用される構造は、MFC クラスから派生していないと、API ヘッダーで定義されます。 これは、DLL とアプリケーション間のインターフェイスの複雑さを軽減し、DLL を C プログラムから使用できるようです。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

