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
ms.openlocfilehash: 8b500f651da1a73040fdb0469f2f023babe25e85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352175"
---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc クラス

[では](../../mfc/reference/chtmleditview-class.md)、MFC ドキュメント ビュー アーキテクチャのコンテキスト内で WebBrowser 編集プラットフォームの機能を提供します。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CHtmlEditDoc : public CDocument
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ドキュドク::CHtmlエディットドック](#chtmleditdoc)|`CHtmlEditDoc` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の項目を取得します。](#getview)|このドキュメントに`CHtmlEditView`添付されているオブジェクトを取得します。|
|[編集](#ismodified)|関連付けられたビューの WebBrowser コントロールに、ユーザーによって変更されたドキュメントが含まれているかどうかを返します。|
|[ド・ド・ド・ス・ド・ス・ド・ス・ド・ス・ド・ス・ド・](#openurl)|URL を開きます。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`CHtmlEditDoc`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxhtml.h

## <a name="chtmleditdocchtmleditdoc"></a><a name="chtmleditdoc"></a>ドキュドク::CHtmlエディットドック

`CHtmlEditDoc` オブジェクトを構築します。

```
CHtmlEditDoc();
```

## <a name="chtmleditdocgetview"></a><a name="getview"></a>次の項目を取得します。

このドキュメントに添付されている[オブジェクト](../../mfc/reference/chtmleditview-class.md)を取得します。

```
virtual CHtmlEditView* GetView() const;
```

### <a name="return-value"></a>戻り値

ドキュメントのオブジェクトへのポインターを`CHtmlEditView`返します。

## <a name="chtmleditdocismodified"></a><a name="ismodified"></a>編集

関連付けられたビューの WebBrowser コントロールに、ユーザーによって変更されたドキュメントが含まれているかどうかを返します。

```
virtual BOOL IsModified();
```

## <a name="chtmleditdocopenurl"></a><a name="openurl"></a>ド・ド・ド・ス・ド・ス・ド・ス・ド・ス・ド・ス・ド・

URL を開きます。

```
virtual BOOL OpenURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
開く URL。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[HTML 編集のサンプル](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
