---
description: '詳細情報: COleLinkingDoc クラス'
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
ms.openlocfilehash: 10cf9bb81c4cbbd324b95a13dc2fa44548266583
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226910"
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
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|`COleLinkingDoc` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleLinkingDoc:: Register](#register)|OLE システム Dll にドキュメントを登録します。|
|[COleLinkingDoc:: Revoke](#revoke)|ドキュメントの登録を取り消します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|指定された埋め込み項目を検索します。|
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|指定されたリンク項目を検索します。|

## <a name="remarks"></a>解説

埋め込みアイテムへのリンクをサポートするコンテナーアプリケーションは、"リンクコンテナー" と呼ばれます。 [OCLIENT](../../overview/visual-cpp-samples.md)サンプルアプリケーションは、リンクコンテナーの一例です。

リンクアイテムのソースが別のドキュメント内の埋め込みアイテムである場合、埋め込みアイテムを編集するには、そのアイテムを含むドキュメントを読み込む必要があります。 このため、リンクコンテナーは、ユーザーがリンクアイテムのソースを編集する場合に、別のコンテナーアプリケーションから起動できる必要があります。 また、アプリケーションでは、プログラムによって起動されたときにドキュメントを作成できるように、 [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) クラスも使用する必要があります。

コンテナーがリンクコンテナーになるようにするには、COleDocument ではなくからドキュメントクラスを派生させ `COleLinkingDoc` ます。 [](../../mfc/reference/coledocument-class.md) 他の OLE コンテナーと同様に、アプリケーションのネイティブデータだけでなく、埋め込みまたはリンクされた項目を格納するためのクラスを設計する必要があります。 また、ネイティブデータを格納するためのデータ構造を設計する必要があります。 `CDocItem`アプリケーションのネイティブデータの派生クラスを定義する場合は、で定義されているインターフェイスを使用して、 `COleDocument` ネイティブデータと OLE データを格納できます。

アプリケーションが別のコンテナーによってプログラムによって起動されるようにするには、 `COleTemplateServer` アプリケーションの派生クラスのメンバーとしてオブジェクトを宣言し `CWinApp` ます。

[!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]

`InitInstance`派生クラスのメンバー関数で `CWinApp` 、ドキュメントテンプレートを作成し、 `COleLinkingDoc` の派生クラスをドキュメントクラスとして指定します。

[!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]

オブジェクト `COleTemplateServer` のメンバー関数を呼び出して、オブジェクトをドキュメントテンプレートに接続 `ConnectTemplate` し、次のようにを呼び出して、すべてのクラスオブジェクトを OLE システムに登録し `COleTemplateServer::RegisterAll` ます。

[!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]

サンプルの `CWinApp` 派生クラスの定義と関数につい `InitInstance` ては、「OCLIENT」を参照してください。H および OCLIENT。MFC サンプル [OCLIENT](../../overview/visual-cpp-samples.md)の CPP。

の使用方法の詳細については `COleLinkingDoc` 、「コンテナーとコンテナー [の実装](../../mfc/containers-implementing-a-container.md) [: 高度な機能](../../mfc/containers-advanced-features.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

`COleLinkingDoc`

## <a name="requirements"></a>要件

**ヘッダー:** afxole

## <a name="colelinkingdoccolelinkingdoc"></a><a name="colelinkingdoc"></a> COleLinkingDoc::COleLinkingDoc

`COleLinkingDoc`OLE システム dll との通信を開始せずにオブジェクトを構築します。

```
COleLinkingDoc();
```

### <a name="remarks"></a>解説

`Register`ドキュメントが開いていることを OLE に通知するには、メンバー関数を呼び出す必要があります。

## <a name="colelinkingdoconfindembeddeditem"></a><a name="onfindembeddeditem"></a> COleLinkingDoc::OnFindEmbeddedItem

指定された名前を持つ埋め込み OLE 項目がドキュメントに含まれているかどうかを判断するために、フレームワークによって呼び出されます。

```
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>パラメーター

*lpszItemName*<br/>
要求された埋め込み OLE 項目の名前へのポインター。

### <a name="return-value"></a>戻り値

指定された項目へのポインター。項目が見つからない場合は NULL。

### <a name="remarks"></a>解説

既定の実装では、指定された名前の項目について、埋め込み項目のリストが検索されます (名前比較では大文字と小文字が区別されます)。 埋め込み OLE 項目を格納または名前付けする独自のメソッドがある場合は、この関数をオーバーライドします。

## <a name="colelinkingdocongetlinkeditem"></a><a name="ongetlinkeditem"></a> COleLinkingDoc::OnGetLinkedItem

指定された名前のリンクサーバー項目がドキュメントに含まれているかどうかを確認するために、フレームワークによって呼び出されます。

```
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>パラメーター

*lpszItemName*<br/>
要求されたリンク OLE 項目の名前へのポインター。

### <a name="return-value"></a>戻り値

指定された項目へのポインター。項目が見つからない場合は NULL。

### <a name="remarks"></a>解説

既定の実装では、 `COleLinkingDoc` 常に NULL が返されます。 この関数は派生クラスでオーバーライドされ、 `COleServerDoc` 指定された名前を持つリンク項目の OLE サーバー項目のリストを検索します (名前比較では大文字と小文字が区別されます)。 リンクサーバー項目を格納または取得する独自のメソッドを実装している場合は、この関数をオーバーライドします。

## <a name="colelinkingdocregister"></a><a name="register"></a> COleLinkingDoc:: Register

ドキュメントが開いていることを OLE システム Dll に通知します。

```
BOOL Register(
    COleObjectFactory* pFactory,
    LPCTSTR lpszPathName);
```

### <a name="parameters"></a>パラメーター

*pFactory*<br/>
OLE ファクトリオブジェクトへのポインター (NULL を指定できます)。

*lpszPathName*<br/>
コンテナードキュメントの完全修飾パスへのポインター。

### <a name="return-value"></a>戻り値

ドキュメントが正常に登録された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

ドキュメントを OLE システム Dll に登録するために、名前付きファイルを作成または開くときに、この関数を呼び出します。 ドキュメントが埋め込みアイテムを表している場合、この関数を呼び出す必要はありません。

アプリケーションでを使用している場合は、、 `COleTemplateServer` `Register` `COleLinkingDoc` 、およびの実装によってが呼び出され `OnNewDocument` `OnOpenDocument` `OnSaveDocument` ます。

## <a name="colelinkingdocrevoke"></a><a name="revoke"></a> COleLinkingDoc:: Revoke

ドキュメントが開かれていないことを OLE システム Dll に通知します。

```cpp
void Revoke();
```

### <a name="remarks"></a>解説

OLE システム Dll を使用してドキュメントの登録を取り消すには、この関数を呼び出します。

名前付きファイルを閉じる場合は、この関数を呼び出す必要がありますが、通常は直接呼び出す必要はありません。 `Revoke` は、、、 `COleLinkingDoc` 、およびの実装によって呼び出され `OnCloseDocument` `OnNewDocument` `OnOpenDocument` `OnSaveDocument` ます。

## <a name="see-also"></a>関連項目

[MFC サンプル OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDocument クラス](../../mfc/reference/coledocument-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)
