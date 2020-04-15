---
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
ms.openlocfilehash: 438bc2a03239946dbfca53d5f2989c731b682ab0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375619"
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
|[ドキュメントを取得します。](#getdocument)|アイテムを含むドキュメントを返します。|
|[CDocItem::イブランク](#isblank)|アイテムに情報が含まれているかどうかを判断します。|

## <a name="remarks"></a>解説

`CDocItem`オブジェクトは、クライアントとサーバーの両方のドキュメントで OLE アイテムを表すために使用されます。

詳細については、「コンテナ :[コンテナの実装 」を参照してください](../../mfc/containers-implementing-a-container.md)。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocItem`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="cdocitemgetdocument"></a><a name="getdocument"></a>ドキュメントを取得します。

アイテムを含むドキュメントを取得します。

```
CDocument* GetDocument() const;
```

### <a name="return-value"></a>戻り値

アイテムを含むドキュメントへのポインター。アイテムがドキュメントの一部でない場合は NULL。

### <a name="remarks"></a>解説

この関数は、派生クラスでオーバーライドされ[、COle](../../mfc/reference/coleclientitem-class.md)ドキュメント[COleServerItem](../../mfc/reference/coleserveritem-class.md)[、COleリングドック](../../mfc/reference/colelinkingdoc-class.md)、または[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)オブジェクトへのポインターを返します。 [COleDocument](../../mfc/reference/coledocument-class.md)

## <a name="cdocitemisblank"></a><a name="isblank"></a>CDocItem::イブランク

既定のシリアル化が発生したときに、フレームワークによって呼び出されます。

```
virtual BOOL IsBlank() const;
```

### <a name="return-value"></a>戻り値

項目に情報が含まれなかった場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

デフォルトでは、`CDocItem`オブジェクトは空白ではありません。 [オブジェクトは](../../mfc/reference/coleclientitem-class.md)から直接派生するため、空白になることがあります`CDocItem`。 ただし、[オブジェクト](../../mfc/reference/coleserveritem-class.md)は常に空白です。 既定では、x または`COleClientItem`y のエクステントを持たないオブジェクトを含む OLE アプリケーションはシリアル化されます。 これは、項目に x または y`IsBlank`のエクステントがない場合のオーバーライドから TRUE を返すことによって行われます。

シリアル化中に他のアクションを実装する場合は、この関数をオーバーライドします。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDocument クラス](../../mfc/reference/coledocument-class.md)<br/>
[COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)<br/>
[クラス](../../mfc/reference/coleclientitem-class.md)
