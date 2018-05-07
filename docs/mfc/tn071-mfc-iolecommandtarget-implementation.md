---
title: 'TN071: MFC IOleCommandTarget の実装 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IOleCommandTarget
dev_langs:
- C++
helpviewer_keywords:
- TN071 [MFC]
- IOleCommandTarget interface [MFC]
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21745762fb6f6eb1eb324013db12207c4b3b81d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tn071-mfc-iolecommandtarget-implementation"></a>テクニカル ノート 71: MFC IOleCommandTarget の実装
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 `IOleCommandTarget`インターフェイス オブジェクトとそのコンテナーに他のコマンドは有効にします。 たとえば、オブジェクトのツールバーのボタンがあるコマンドのように**印刷**、**印刷プレビュー**、**保存**、 `New`、および**ズーム**. このようなオブジェクトをサポートするコンテナーに埋め込まれたかどうか`IOleCommandTarget`、オブジェクトでしたそのボタンを有効にして、コマンドに、ユーザーがクリックされたときに処理するためのコンテナーに転送します。 コンテナーが、埋め込みオブジェクト自体を印刷する場合、その行うことができるこの要求を介してコマンドを送信することによって、`IOleCommandTarget`埋め込みオブジェクトのインターフェイスです。  
  
 `IOleCommandTarget` サーバーでメソッドを呼び出すクライアントによって使用されることで、オートメーションのようなインターフェイスです。 ただしを使用して`IOleCommandTarget`通常高価なを使用するプログラマが必要ないために、オートメーション インターフェイスを使用して呼び出しを行うのオーバーヘッドを削減できます`Invoke`メソッドの`IDispatch`します。  
  
 MFC では、`IOleCommandTarget`インターフェイスは、Active ドキュメント コンテナーは、サーバーに使用できるように Active ドキュメント サーバーで使用します。 Active ドキュメント サーバー クラス`CDocObjectServerItem`、MFC インターフェイス マップを使用して (を参照してください[TN038: MFC/OLE IUnknown の実装](../mfc/tn038-mfc-ole-iunknown-implementation.md)) を実装する、`IOleCommandTarget`インターフェイスです。  
  
 `IOleCommandTarget` 実装されても、 **COleFrameHook**クラスです。 **COleFrameHook**インプレースでのフレーム ウィンドウの機能を実装するドキュメントに未記載の MFC クラスのコンテナーを編集します。 **COleFrameHook**も MFC インターフェイス マップを使用して実装する、`IOleCommandTarget`インターフェイスです。 **COleFrameHook**の実装の`IOleCommandTarget`OLE コマンドは転送`COleDocObjectItem`-Active ドキュメント コンテナーを派生します。 これにより、Active ドキュメント サーバーからメッセージを受信するすべての MFC Active ドキュメント コンテナーです。  
  
## <a name="mfc-ole-command-maps"></a>MFC OLE コマンド マップ  
 MFC 活かすことができますの`IOleCommandTarget`MFC OLE を使用してコマンドをマップします。 OLE コマンドではメッセージされる OLE コマンドをコマンド マップを含んでいるクラスのメンバー関数にマップするためのマップと同じようにします。 この作業をするためには、グループを指定する、OLE コマンドを処理するコマンドや OLE コマンドのコマンド ID のコマンド マップにマクロを配置、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) OLE コマンドが受信したときに送信されるメッセージ。 MFC には、標準の OLE コマンドのいくつかの定義済みマクロも用意されています。 一連の標準の OLE 用に設計された最初のコマンドを使用して Microsoft Office アプリケーションを参照してください docobj.h で定義されている OLECMDID 列挙します。  
  
 OLE コマンド マップを含む MFC アプリケーションによって OLE コマンドが受信されると、MFC は、アプリケーションのマップで、要求されたコマンドのコマンド ID およびコマンド グループを見つけようと試みます。 一致が見つかった場合、 **WM_COMMAND**要求されたコマンドの ID を持つコマンド マップを含むアプリケーションにメッセージをディスパッチします。 (の説明を参照して`ON_OLECMD`以下です)。これにより、アプリケーションにディスパッチ OLE コマンドに変換**WM_COMMAND** MFC でのメッセージ。 **WM_COMMAND** MFC 標準を使用して、アプリケーションのメッセージ マップを通じてメッセージがルーティングし、[コマンド ルーティング](../mfc/command-routing.md)アーキテクチャ。  
  
 メッセージ マップとは異なり、MFC OLE コマンド マップは ClassWizard でサポートされていません。 MFC 開発者 OLE コマンド マップのサポートと OLE コマンド マップ エントリを手動で追加する必要があります。 OLE コマンド マップに追加できますが、任意のクラスで MFC Active ドキュメント サーバー、 **WM_COMMAND**アクティブなドキュメントは、コンテナーに、インプレース アクティブ時のメッセージのルーティングのチェーン。 これらのクラスから派生した、アプリケーションのクラスを含める[CWinApp](../mfc/reference/cwinapp-class.md)、 [CView](../mfc/reference/cview-class.md)、 [CDocument](../mfc/reference/cdocument-class.md)、および[COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)です。 Active ドキュメント コンテナー OLE コマンド マップのみを追加できるを[関数](../mfc/reference/coledocobjectitem-class.md)-クラスを派生します。 Active ドキュメント コンテナーでも、 **WM_COMMAND**でメッセージ マップへのメッセージのディスパッチのみ、 `COleDocObjectItem`-クラスを派生します。  
  
## <a name="ole-command-map-macros"></a>OLE コマンド マップ マクロ  
 コマンド マップ機能をクラスに追加するのにには、次のマクロを使用します。  
  
```  
 
DECLARE_OLECMD_MAP ()  
 
```  
  
 このマクロは、コマンド マップを含んでいるクラスのクラス宣言 (通常、ヘッダー ファイル内) に移動します。  
  
```  
 
BEGIN_OLECMD_MAP(
theClass  ,   baseClass)  
 
```  
  
 `theClass`  
 コマンド マップを含んでいるクラスの名前。  
  
 `baseClass`  
 コマンド マップを含んでいるクラスの基本クラスの名前です。  
  
 このマクロは、コマンド マップの開始をマークします。 コマンド マップを含んでいるクラスの実装ファイルでこのマクロを使用します。  
  
```  
 
END_OLECMD_MAP()  
 
```  
  
 このマクロは、コマンド マップの最後をマークします。 コマンド マップを含んでいるクラスの実装ファイルでこのマクロを使用します。 このマクロは常に従う必要があります、**必ず**マクロです。  
  
```  
 
ON_OLECMD(
pguid  ,   
olecmdid  ,
    id)  
 
```  
  
 `pguid`  
 OLE コマンドのコマンドのグループの GUID へのポインター。 このパラメーターは**NULL**の標準の OLE コマンド グループ。  
  
 *olecmdid*  
 呼び出されるコマンドの OLE コマンド ID。  
  
 `id`  
 ID、 **WM_COMMAND**この OLE コマンドが呼び出されたときに、コマンド マップを含んでいるアプリケーションに送信されるメッセージ。  
  
 使用して、`ON_OLECMD`マクロ OLE のエントリを追加するコマンド マップでのコマンドを処理します。 OLE コマンドが受信されると、変換を指定した**WM_COMMAND**メッセージし、標準的な MFC のコマンド ルーティングのアーキテクチャを使用して、アプリケーションのメッセージ マップを経由してルーティングします。  
  
## <a name="example"></a>例  
 次の例を処理する MFC Active ドキュメント サーバーに OLE コマンド処理の機能を追加する方法を示しています、[います。](http://msdn.microsoft.com/library/windows/desktop/ms691264) OLE コマンド。 この例では、Active ドキュメント サーバーは、MFC アプリケーションを生成する AppWizard を使用することを前提としています。  
  
1.  `CView`-派生したクラスのヘッダー ファイルに追加し、`DECLARE_OLECMD_MAP`クラス宣言にマクロです。  
  
    > [!NOTE]
    >  使用して、 `CView`-クラスを派生クラスでは、Active ドキュメント サーバーでは、いずれかになっているため、 **WM_COMMAND**メッセージ ルーティングのチェーン。  
  
 ```  
    class CMyServerView : public CView  
 {  
    protected: // create from serialization only  
    CMyServerView();
DECLARE_DYNCREATE(CMyServerView)  
    DECLARE_OLECMD_MAP() 
 . . .  
 };  
 ```  
  
2.  実装ファイルで、 `CView`-派生クラスに追加、`BEGIN_OLECMD_MAP`と`END_OLECMD_MAP`マクロ。  
  
 ```  
    BEGIN_OLECMD_MAP(CMyServerView, CView)  
 
    END_OLECMD_MAP() 
 ```  
  
3.  標準の OLE print コマンドを処理するための追加、 [ON_OLECMD](reference/message-map-macros-mfc.md#on_olecmd) 、標準の印刷コマンドを OLE コマンド ID を指定するコマンド マップにマクロと**ID_FILE_PRINT**の**WM_COMMAND** Id です。 **ID_FILE_PRINT** AppWizard で生成された MFC アプリケーションから印刷コマンド ID に使用される標準には。  
  
 ```  
    BEGIN_OLECMD_MAP(CMyServerView,
    CView)  
    ON_OLECMD(NULL,
    OLECMDID_PRINT,
    ID_FILE_PRINT) 
    END_OLECMD_MAP() 
 ```  
  
 Afxdocob.h で定義されている標準の OLE コマンド マクロのいずれかの代わりに使用できることに注意してください、`ON_OLECMD`マクロのため**います。**標準 OLE コマンド id です。 `ON_OLECMD_PRINT`マクロと同じタスクを実施、`ON_OLECMD`上に示したマクロです。  
  
 コンテナー アプリケーションがこのサーバーに送信すると、**います。**を通じてサーバーのコマンド`IOleCommandTarget`により、サーバー アプリケーションを印刷する、サーバーでインターフェイス、MFC の印刷コマンド ハンドラーが呼び出されます。 Active ドキュメント コンテナーの前述の手順で追加された印刷コマンドを呼び出すコードは、次のようになります。  
  
```  
void CContainerCntrItem::DoOleCmd()  
{  
    IOleCommandTarget *pCmd = NULL;  
    HRESULT hr = E_FAIL;  
    OLECMD ocm={OLECMDID_PRINT, 0};  
 
    hr = m_lpObject->QueryInterface(IID_IOleCommandTarget,reinterpret_cast<void**>(&pCmd));

    if(FAILED(hr)) 
    return; 
 
    hr = pCmd->QueryStatus(NULL, 1, &ocm, NULL);

    if(SUCCEEDED(hr)&& (ocm.cmdf& OLECMDF_ENABLED))  
 { *//Command is available and enabled so call it  
    COleVariant vIn;  
    COleVariant vOut;  
    hr = pCmd->Exec(NULL, OLECMDID_PRINT,  
    OLECMDEXECOPT_DODEFAULT, &vIn, &vOut);

    ASSERT(SUCCEEDED(hr));

 }  
    pCmd->Release();

} 
```  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

