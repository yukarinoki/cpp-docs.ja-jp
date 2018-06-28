---
title: 直接クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
dev_langs:
- C++
helpviewer_keywords:
- COleLinkingDoc [MFC], COleLinkingDoc
- COleLinkingDoc [MFC], Register
- COleLinkingDoc [MFC], Revoke
- COleLinkingDoc [MFC], OnFindEmbeddedItem
- COleLinkingDoc [MFC], OnGetLinkedItem
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 843c79d9b3c7ffeb0ceef7338132048ac51d52ef
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039974"
---
# <a name="colelinkingdoc-class"></a>直接クラス
OLE コンテナー ドキュメントの基底クラスです。OLE コンテナー ドキュメントは、ドキュメントが保持する埋め込みアイテムへのリンクをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|`COleLinkingDoc` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleLinkingDoc::Register](#register)|OLE システム Dll をドキュメントを登録します。|  
|[COleLinkingDoc::Revoke](#revoke)|ドキュメントの登録を取り消します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|指定された埋め込み項目を検索します。|  
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|指定したリンク アイテムを検索します。|  
  
## <a name="remarks"></a>Remarks  
 埋め込みアイテムへのリンクをサポートするコンテナー アプリケーションは、コンテナーと呼ばれる、"リンクします" [OCLIENT](../../visual-cpp-samples.md)サンプル アプリケーションは、リンクのコンテナーの例を示します。  
  
 リンクされた項目のソースが別のドキュメントに埋め込まれたアイテムの場合は、そのコンテナーのドキュメントを編集しようとする埋め込みアイテムの順序で読み込む必要があります。 このため、リンク コンテナーは、ユーザーがリンクされた項目のソースを編集するときに別のコンテナー アプリケーションによって起動できる必要があります。 アプリケーションを使用する必要がありますも、 [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)クラスのプログラムで起動されたときにドキュメントを作成できるようにします。  
  
 ドキュメント クラスを派生するのには、コンテナーのリンクのコンテナー、`COleLinkingDoc`の代わりに[COleDocument](../../mfc/reference/coledocument-class.md)です。 その他の OLE コンテナーと同様、アプリケーションのネイティブ データだけでなく埋め込みまたはリンクされた項目を格納するため、クラスをデザインする必要があります。 また、ネイティブ データを格納するためのデータ構造を設計する必要があります。 定義する場合、 `CDocItem`-派生クラスをアプリケーションのネイティブ データによって定義されたインターフェイスを使用して`COleDocument`ネイティブ データだけでなく、OLE データを格納します。  
  
 別のコンテナーをプログラムで起動されるようにアプリケーションを許可するのには、宣言、`COleTemplateServer`オブジェクトをアプリケーションのメンバーとして`CWinApp`-派生クラス。  
  
 [!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]  
  
 `InitInstance`のメンバー関数、 `CWinApp`-派生クラスでは、ドキュメント テンプレートを作成し、指定、 `COleLinkingDoc`-ドキュメント クラスとクラスを派生します。  
  
 [!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]  
  
 接続、`COleTemplateServer`オブジェクトを呼び出して、オブジェクトのドキュメント テンプレートを`ConnectTemplate`メンバー関数、およびすべてのクラス オブジェクトを呼び出すことによって OLE システムに登録`COleTemplateServer::RegisterAll`:  
  
 [!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]  
  
 サンプルの`CWinApp`-派生したクラス定義と`InitInstance`関数 OCLIENT を参照してください。H と OCLIENT です。MFC サンプル CPP [OCLIENT](../../visual-cpp-samples.md)です。  
  
 使用する方法についての`COleLinkingDoc`、記事を参照して[コンテナー: コンテナーの実装](../../mfc/containers-implementing-a-container.md)と[コンテナー: 高度な機能](../../mfc/containers-advanced-features.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxole.h  
  
##  <a name="colelinkingdoc"></a>  COleLinkingDoc::COleLinkingDoc  
 構築、 `COleLinkingDoc` OLE システム Dll との通信を開始せずオブジェクト。  
  
```  
COleLinkingDoc();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出す必要があります、 `Register` OLE ドキュメントが開いていることを通知するメンバー関数。  
  
##  <a name="onfindembeddeditem"></a>  COleLinkingDoc::OnFindEmbeddedItem  
 ドキュメントに指定した名前 OLE 埋め込みアイテムが含まれるかどうかを判断するためにフレームワークによって呼び出されます。  
  
```  
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszItemName*  
 埋め込み OLE アイテムの名前へのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定された項目へのポインター**NULL**場合は、項目は見つかっていません。  
  
### <a name="remarks"></a>Remarks  
 既定の実装では、指定した名前 (名前の比較では大文字小文字を区別) を持つ項目の埋め込まれた項目の一覧を検索します。 独自のメソッドの格納や埋め込み OLE アイテムの名前を付ける必要がある場合は、この関数をオーバーライドします。  
  
##  <a name="ongetlinkeditem"></a>  COleLinkingDoc::OnGetLinkedItem  
 ドキュメントに指定した名前のリンク サーバー項目が含まれているかどうか確認するためにフレームワークによって呼び出されます。  
  
```  
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszItemName*  
 リンクされた OLE アイテムの名前へのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定された項目へのポインター**NULL**場合は、項目は見つかっていません。  
  
### <a name="remarks"></a>Remarks  
 既定値`COleLinkingDoc`実装は常に返します**NULL**です。 この関数は、派生クラスでオーバーライドされる`COleServerDoc`のリンクされた項目の指定した名前 (名前の比較では大文字小文字を区別) OLE サーバー項目のリストを検索します。 格納や、リンク サーバーのアイテムを取得する独自のメソッドを実装している場合は、この関数をオーバーライドします。  
  
##  <a name="register"></a>  COleLinkingDoc::Register  
 ドキュメントが開かれている OLE システム Dll に通知します。  
  
```  
BOOL Register(
    COleObjectFactory* pFactory,  
    LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFactory*  
 OLE ファクトリ オブジェクトへのポインター (できます**NULL**)。  
  
 *終了*  
 コンテナー ドキュメントの完全修飾パスへのポインター。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ドキュメントが正常に登録します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 作成または OLE システム Dll で、ドキュメントを登録する名前付きのファイルを開くときは、この関数を呼び出します。 ドキュメントが埋め込まれた項目を表す場合は、この関数を呼び出す必要はありません。  
  
 使用している場合`COleTemplateServer`、アプリケーションで`Register`によって呼び出されます`COleLinkingDoc`の実装の`OnNewDocument`、 `OnOpenDocument`、および`OnSaveDocument`です。  
  
##  <a name="revoke"></a>  COleLinkingDoc::Revoke  
 OLE システム Dll にドキュメントが開いていないことが通知されます。  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Remarks  
 OLE システム Dll のドキュメントの登録を取り消すには、この関数を呼び出します。  
  
 名前付きのファイルを閉じるときに、この関数を呼び出す必要がありますが、通常必要はありませんメソッドを直接呼び出す。 `Revoke` によって呼び出されます`COleLinkingDoc`の実装の`OnCloseDocument`、 `OnNewDocument`、 `OnOpenDocument`、および`OnSaveDocument`です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル OCLIENT](../../visual-cpp-samples.md)   
 [COleDocument クラス](../../mfc/reference/coledocument-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)
