---
title: COM マップマクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
ms.openlocfilehash: 100402e17ca1bee5f338c37f2315fbc4898a713e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833583"
---
# <a name="com-map-macros"></a>COM マップマクロ

これらのマクロは、COM インターフェイスマップを定義します。

|マクロ|説明|
|-|-|
|[BEGIN_COM_MAP](#begin_com_map)|COM インターフェイスマップエントリの先頭をマークします。|
|[END_COM_MAP](#end_com_map)|COM インターフェイスマップエントリの終了をマークします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom. h

## <a name="begin_com_map"></a><a name="begin_com_map"></a> BEGIN_COM_MAP

COM マップは、を介してクライアントに対してオブジェクトのインターフェイスを公開するメカニズムです `QueryInterface` 。

```
BEGIN_COM_MAP(x)
```

### <a name="parameters"></a>パラメーター

*x*<br/>
からインターフェイスを公開するクラスオブジェクトの名前。

### <a name="remarks"></a>解説

[CComObjectRootEx:: InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) は、COM マップ内のインターフェイスのポインターのみを返します。 BEGIN_COM_MAP マクロを使用してインターフェイスマップを開始し、 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) マクロまたはそのバリアントの1つを使用してインターフェイスのエントリを追加し、 [END_COM_MAP](#end_com_map) マクロを使用してマップを完了します。

### <a name="example"></a>例

ATL [BEEPER](../../overview/visual-cpp-samples.md) サンプルから:

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="end_com_map"></a><a name="end_com_map"></a> END_COM_MAP

COM インターフェイスマップの定義を終了します。

```
END_COM_MAP()
```

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)<br/>
[COM マップのグローバル関数](../../atl/reference/com-map-global-functions.md)
