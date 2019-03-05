---
title: CHtmlEditDoc クラス
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
ms.openlocfilehash: f468de46cf6d8a8bfcd60521df8b1076a98f0735
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285335"
---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc クラス

[CHtmlEditView](../../mfc/reference/chtmleditview-class.md)MFC のドキュメント/ビュー アーキテクチャのコンテキストで WebBrowser 編集プラットフォームの機能を提供します。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CHtmlEditDoc : public CDocument
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|`CHtmlEditDoc` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHtmlEditDoc::GetView](#getview)|取得、`CHtmlEditView`オブジェクトはこのドキュメントにアタッチします。|
|[CHtmlEditDoc::IsModified](#ismodified)|関連するビューの WebBrowser コントロールがユーザーによって変更されたドキュメントを含むかどうかを返します。|
|[CHtmlEditDoc::OpenURL](#openurl)|URL が開きます。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`CHtmlEditDoc`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxhtml.h

##  <a name="chtmleditdoc"></a>  CHtmlEditDoc::CHtmlEditDoc

`CHtmlEditDoc` オブジェクトを構築します。

```
CHtmlEditDoc();
```

##  <a name="getview"></a>  CHtmlEditDoc::GetView

取得、 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)オブジェクトはこのドキュメントにアタッチします。

```
virtual CHtmlEditView* GetView() const;
```

### <a name="return-value"></a>戻り値

ドキュメントへのポインターを返します`CHtmlEditView`オブジェクト。

##  <a name="ismodified"></a>  CHtmlEditDoc::IsModified

関連するビューの WebBrowser コントロールがユーザーによって変更されたドキュメントを含むかどうかを返します。

```
virtual BOOL IsModified();
```

##  <a name="openurl"></a>  CHtmlEditDoc::OpenURL

URL が開きます。

```
virtual BOOL OpenURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>パラメーター

*lpszURL*<br/>
開くための URL。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

## <a name="see-also"></a>関連項目

[HTMLEdit サンプル](../../visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
