---
title: COM マップに関するマクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
ms.openlocfilehash: dbb84814c6865b5b666a8b3a1162e81a211de1eb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280707"
---
# <a name="com-map-macros"></a>COM マップに関するマクロ

これらのマクロは、COM インターフェイス マップを定義します。

|||
|-|-|
|[BEGIN_COM_MAP](#begin_com_map)|COM インターフェイスのマップ エントリの先頭をマークします。|
|[END_COM_MAP](#end_com_map)|COM インターフェイスのマップ エントリの終了を示します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="begin_com_map"></a>  BEGIN_COM_MAP

COM マップを介してクライアントにオブジェクトのインターフェイスを公開するメカニズムは、`QueryInterface`します。

```
BEGIN_COM_MAP(x)
```

### <a name="parameters"></a>パラメーター

*x*<br/>
[in]インターフェイスを公開するのには、クラス オブジェクトの名前。

### <a name="remarks"></a>Remarks

[CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface)のみ COM マップ内のインターフェイス ポインターを返します。 BEGIN_COM_MAP マクロとインターフェイス マップを開始、使用して、インターフェイスの各エントリを追加、 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry)マクロ、またはそのバリエーションの 1 つを含むマップを完了して、 [END_COM_MAP](#end_com_map)マクロ。

### <a name="example"></a>例

ATL から[BEEPER](../../visual-cpp-samples.md)サンプル。

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

##  <a name="end_com_map"></a>  END_COM_MAP

COM インターフェイス マップの定義を終了します。

```
END_COM_MAP()
```

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)<br/>
[COM マップに関するグローバル関数](../../atl/reference/com-map-global-functions.md)
