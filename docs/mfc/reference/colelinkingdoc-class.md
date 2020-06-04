---
title: COleLinkingDoc クラス
ms.date: 11/04/2016
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
helpviewer_keywords:
- COleLinkingDoc [MFC], COleLinkingDoc
- COleLinkingDoc [MFC], Register
- COleLinkingDoc [MFC], Revoke
- COleLinkingDoc [MFC], OnFindEmbeddedItem
- COleLinkingDoc [MFC], OnGetLinkedItem
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
ms.openlocfilehash: 1fad986b7e7304075cacb0b5ced9feeb8af4664f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753842"
---
# <a name="colelinkingdoc-class"></a>COleLinkingDoc クラス

OLE コンテナー ドキュメントの基底クラスです。OLE コンテナー ドキュメントは、ドキュメントが保持する埋め込みアイテムへのリンクをサポートします。

## <a name="syntax"></a>構文

```
class COleLinkingDoc : public COleDocument
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コレクリンクドック:::コレクリンクドック](#colelinkingdoc)|`COleLinkingDoc` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[登録](#register)|OLE システム DLL にドキュメントを登録します。|
|[取り消し](#revoke)|ドキュメントの登録を取り消します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ドキュメントを検索します。](#onfindembeddeditem)|指定した埋め込みアイテムを検索します。|
|[ド・コレクトリンクド::オンゲットリンクトアイテム](#ongetlinkeditem)|指定したリンク アイテムを検索します。|

## <a name="remarks"></a>解説

埋め込みアイテムへのリンクをサポートするコンテナー アプリケーションを "リンク コンテナー" と呼びます。 [OCLIENT](../../overview/visual-cpp-samples.md)サンプル アプリケーションは、リンク コンテナーの例です。

リンクされたアイテムのソースが別のドキュメントの埋め込みアイテムである場合、埋め込みアイテムを編集するには、そのドキュメントを含むドキュメントを読み込む必要があります。 このため、ユーザーがリンク アイテムのソースを編集する場合は、リンク コンテナーを別のコンテナー アプリケーションで起動できる必要があります。 アプリケーションは、プログラムで起動したときにドキュメントを作成できるように[、COleTemplateServer](../../mfc/reference/coletemplateserver-class.md)クラスも使用する必要があります。

コンテナーをリンク コンテナーにするには[、COleDocument](../../mfc/reference/coledocument-class.md)ではなくから`COleLinkingDoc`ドキュメント クラスを派生させます。 他の OLE コンテナーと同様に、埋め込みアイテムやリンクアイテムだけでなく、アプリケーションのネイティブ データを格納するためのクラスを設計する必要があります。 また、ネイティブ データを格納するためのデータ構造を設計する必要があります。 アプリケーションのネイティブ`CDocItem`データに対して -derived クラスを定義する場合は、 で`COleDocument`定義されたインターフェイスを使用して、ネイティブ データと OLE データを格納できます。

別のコンテナーによってアプリケーションをプログラムで起動できるようにするには、オブジェクトを`COleTemplateServer`アプリケーションの派生クラスの`CWinApp`メンバーとして宣言します。

[!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]

派生クラス`InitInstance`のメンバー関数で`CWinApp`、ドキュメント テンプレートを作成し、`COleLinkingDoc`ドキュメント クラスとして -derived クラスを指定します。

[!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]

`COleTemplateServer`オブジェクトの`ConnectTemplate`メンバー関数を呼び出して、オブジェクトをドキュメント テンプレートに接続し、 を呼び出`COleTemplateServer::RegisterAll`して、OLE システムにクラス オブジェクトをすべて登録します。

[!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]

サンプル`CWinApp`派生クラス定義と`InitInstance`関数については、OCLIENT を参照してください。H と OCLIENT.MFC サンプル[OCLIENT](../../overview/visual-cpp-samples.md)の CPP を参照してください。

の詳細`COleLinkingDoc`については、「 コンテナー :[コンテナーとコンテナーの実装](../../mfc/containers-implementing-a-container.md) [: 拡張機能](../../mfc/containers-advanced-features.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

`COleLinkingDoc`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="colelinkingdoccolelinkingdoc"></a><a name="colelinkingdoc"></a>コレクリンクドック:::コレクリンクドック

OLE システム`COleLinkingDoc`DLL との通信を開始せずにオブジェクトを構築します。

```
COleLinkingDoc();
```

### <a name="remarks"></a>解説

ドキュメントが`Register`開いていることを OLE に通知するには、メンバー関数を呼び出す必要があります。

## <a name="colelinkingdoconfindembeddeditem"></a><a name="onfindembeddeditem"></a>ドキュメントを検索します。

指定した名前の埋め込み OLE アイテムがドキュメントに含まれているかどうかを調べるには、フレームワークによって呼び出されます。

```
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
要求された埋め込み OLE アイテムの名前へのポインター。

### <a name="return-value"></a>戻り値

指定された項目へのポインター。項目が見つからない場合は NULL。

### <a name="remarks"></a>解説

既定の実装では、埋め込みアイテムのリストで、指定した名前の項目を検索します (名前の比較では大文字と小文字が区別されます)。 埋め込み OLE アイテムを格納または名前付けする独自のメソッドがある場合は、この関数をオーバーライドします。

## <a name="colelinkingdocongetlinkeditem"></a><a name="ongetlinkeditem"></a>ド・コレクトリンクド::オンゲットリンクトアイテム

指定した名前のリンク サーバー アイテムがドキュメントに含まれているかどうかを確認するために、フレームワークによって呼び出されます。

```
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
要求されたリンク OLE アイテムの名前へのポインター。

### <a name="return-value"></a>戻り値

指定された項目へのポインター。項目が見つからない場合は NULL。

### <a name="remarks"></a>解説

既定`COleLinkingDoc`の実装では、常に NULL が返されます。 この関数は、指定した名前のリンク`COleServerDoc`アイテムを OLE サーバー アイテムの一覧で検索するために、派生クラスでオーバーライドされます (名前の比較では大文字と小文字が区別されます)。 リンク サーバーアイテムを格納または取得する独自のメソッドを実装している場合は、この関数をオーバーライドします。

## <a name="colelinkingdocregister"></a><a name="register"></a>登録

ドキュメントが開いていることを OLE システム DLL に通知します。

```
BOOL Register(
    COleObjectFactory* pFactory,
    LPCTSTR lpszPathName);
```

### <a name="parameters"></a>パラメーター

*pFactory*<br/>
OLE ファクトリ オブジェクトへのポインター (NULL を指定できます)。

*パス名*<br/>
コンテナー ドキュメントの完全修飾パスへのポインター。

### <a name="return-value"></a>戻り値

ドキュメントが正常に登録された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

OLE システム DLL にドキュメントを登録する名前付きファイルを作成または開くときに、この関数を呼び出します。 ドキュメントが埋め込みアイテムを表す場合は、この関数を呼び出す必要はありません。

アプリケーションで使用`COleTemplateServer`している場合`Register`は、 、`COleLinkingDoc``OnNewDocument``OnOpenDocument`および の 実装によって呼び出されます。 `OnSaveDocument`

## <a name="colelinkingdocrevoke"></a><a name="revoke"></a>取り消し

ドキュメントが開かなくなったことを OLE システム DLL に通知します。

```cpp
void Revoke();
```

### <a name="remarks"></a>解説

OLE システム DLL に対するドキュメントの登録を取り消します。

名前付きファイルを閉じるときにこの関数を呼び出す必要がありますが、通常は直接呼び出す必要はありません。 `Revoke`は、 `COleLinkingDoc` `OnCloseDocument` `OnNewDocument`、 、 、`OnOpenDocument`および の実装によって`OnSaveDocument`呼び出されます。

## <a name="see-also"></a>関連項目

[サンプル O クライアント](../../overview/visual-cpp-samples.md)<br/>
[COleDocument クラス](../../mfc/reference/coledocument-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cdoctemplate-class.md)
