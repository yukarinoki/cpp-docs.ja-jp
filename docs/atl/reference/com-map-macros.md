---
title: COM マップ マクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
ms.openlocfilehash: 191a0ba0aeda6ad18cdac7ba14f7ab5f3b2282f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326604"
---
# <a name="com-map-macros"></a>COM マップ マクロ

これらのマクロは、COM インターフェイス マップを定義します。

|||
|-|-|
|[BEGIN_COM_MAP](#begin_com_map)|COM インターフェイス マップ エントリの先頭を示します。|
|[END_COM_MAP](#end_com_map)|COM インターフェイス マップ エントリの末尾をマークします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="begin_com_map"></a><a name="begin_com_map"></a>BEGIN_COM_MAP

COM マップは、 を通じて`QueryInterface`オブジェクトのインターフェイスをクライアントに公開する機構です。

```
BEGIN_COM_MAP(x)
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]インターフェイスを公開するクラス オブジェクトの名前。

### <a name="remarks"></a>解説

[COM](ccomobjectrootex-class.md#internalqueryinterface)マップ内のインターフェイスのポインターのみを返します。 BEGIN_COM_MAP マクロを使用してインターフェイス マップを開始し[、COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry)マクロまたはそのバリアントを使用して各インターフェイスのエントリを追加し[、END_COM_MAP](#end_com_map)マクロを使用してマップを完成させます。

### <a name="example"></a>例

ATL[ビーパーサンプルから](../../overview/visual-cpp-samples.md):

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="end_com_map"></a><a name="end_com_map"></a>END_COM_MAP

COM インターフェイス マップの定義を終了します。

```
END_COM_MAP()
```

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)<br/>
[COM マップ グローバル関数](../../atl/reference/com-map-global-functions.md)
