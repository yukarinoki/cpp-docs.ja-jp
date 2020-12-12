---
description: '詳細情報: CHtmlEditDoc クラス'
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
ms.openlocfilehash: 5fb8187ff7925efc5bdfa6a0079a8ec4b186ae63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115314"
---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc クラス

[CHtmlEditView](../../mfc/reference/chtmleditview-class.md)を使用すると、は、MFC のドキュメント/ビューアーキテクチャのコンテキスト内で WebBrowser 編集プラットフォームの機能を提供します。

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
|[CHtmlEditDoc:: GetView](#getview)|`CHtmlEditView`このドキュメントにアタッチされているオブジェクトを取得します。|
|[CHtmlEditDoc:: IsModified](#ismodified)|関連付けられたビューの WebBrowser コントロールに、ユーザーによって変更されたドキュメントが含まれているかどうかを示す値を返します。|
|[CHtmlEditDoc:: OpenURL](#openurl)|URL を開きます。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`CHtmlEditDoc`

## <a name="requirements"></a>要件

**ヘッダー:** afxhtml.h

## <a name="chtmleditdocchtmleditdoc"></a><a name="chtmleditdoc"></a> CHtmlEditDoc::CHtmlEditDoc

`CHtmlEditDoc` オブジェクトを構築します。

```
CHtmlEditDoc();
```

## <a name="chtmleditdocgetview"></a><a name="getview"></a> CHtmlEditDoc:: GetView

このドキュメントにアタッチされている [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) オブジェクトを取得します。

```
virtual CHtmlEditView* GetView() const;
```

### <a name="return-value"></a>戻り値

ドキュメントのオブジェクトへのポインターを返し `CHtmlEditView` ます。

## <a name="chtmleditdocismodified"></a><a name="ismodified"></a> CHtmlEditDoc:: IsModified

関連付けられたビューの WebBrowser コントロールに、ユーザーによって変更されたドキュメントが含まれているかどうかを示す値を返します。

```
virtual BOOL IsModified();
```

## <a name="chtmleditdocopenurl"></a><a name="openurl"></a> CHtmlEditDoc:: OpenURL

URL を開きます。

```
virtual BOOL OpenURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>パラメーター

*lpszURL*<br/>
開く URL。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[HTMLEdit サンプル](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
