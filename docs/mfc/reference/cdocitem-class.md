---
description: '詳細情報: CDocItem クラス'
title: CDocItem クラス
ms.date: 11/04/2016
f1_keywords:
- CDocItem
- AFXOLE/CDocItem
- AFXOLE/CDocItem::GetDocument
- AFXOLE/CDocItem::IsBlank
helpviewer_keywords:
- CDocItem [MFC], GetDocument
- CDocItem [MFC], IsBlank
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
ms.openlocfilehash: 9e126d4351248165a3961739c13cc6ce7330c10c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185142"
---
# <a name="cdocitem-class"></a>CDocItem クラス

ドキュメント アイテムの基底クラスであり、ドキュメント データのコンポーネントです。

## <a name="syntax"></a>構文

```
class CDocItem : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDocItem:: GetDocument](#getdocument)|項目を含むドキュメントを返します。|
|[CDocItem:: IsBlank](#isblank)|項目に情報が含まれているかどうかを判断します。|

## <a name="remarks"></a>解説

`CDocItem` オブジェクトは、クライアントとサーバーの両方のドキュメントで OLE 項目を表すために使用されます。

詳細については、「コンテナー [: コンテナーの実装](../../mfc/containers-implementing-a-container.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocItem`

## <a name="requirements"></a>要件

**ヘッダー:** afxole

## <a name="cdocitemgetdocument"></a><a name="getdocument"></a> CDocItem:: GetDocument

項目を含むドキュメントを取得するには、この関数を呼び出します。

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>戻り値

項目を格納しているドキュメントへのポインター。項目がドキュメントの一部でない場合は NULL。

### <a name="remarks"></a>解説

この関数は、 [COleClientItem](../../mfc/reference/coleclientitem-class.md) と [COleServerItem](../../mfc/reference/coleserveritem-class.md)の派生クラスでオーバーライドされ、 [COleDocument](../../mfc/reference/coledocument-class.md)、 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)、または [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) のいずれかのオブジェクトへのポインターを返します。

## <a name="cdocitemisblank"></a><a name="isblank"></a> CDocItem:: IsBlank

既定のシリアル化が発生したときにフレームワークによって呼び出されます。

```
virtual BOOL IsBlank() const;
```

### <a name="return-value"></a>戻り値

項目に情報が含まれていない場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

既定で `CDocItem` は、オブジェクトは空白ではありません。 [COleClientItem](../../mfc/reference/coleclientitem-class.md) オブジェクトは、から直接派生しているため、空白になることがあり `CDocItem` ます。 ただし、 [COleServerItem](../../mfc/reference/coleserveritem-class.md) オブジェクトは常に空白です。 既定では、 `COleClientItem` x または y エクステントのないオブジェクトを含む OLE アプリケーションはシリアル化されます。 これは `IsBlank` 、項目に x または y の範囲がない場合に、のオーバーライドから TRUE を返すことによって行われます。

シリアル化中に他のアクションを実装する場合は、この関数をオーバーライドします。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDocument クラス](../../mfc/reference/coledocument-class.md)<br/>
[COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)<br/>
[COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)
