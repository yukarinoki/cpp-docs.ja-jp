---
title: _U_RECTクラス
ms.date: 11/04/2016
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
ms.openlocfilehash: 8a4d5b2a770b3f0ecfe10be0fbad22a702aa0531
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325809"
---
# <a name="_u_rect-class"></a>_U_RECTクラス

この引数アダプター クラスでは`RECT`、ポインターまたは参照をポインターの観点から実装された関数に渡すことができます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class _U_RECT
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[_U_RECT::_U_RECT](#_u_rect___u_rect)|コンストラクターです。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[_U_RECT::m_lpRect](#_u_rect__m_lprect)|へのポインタです`RECT`。|

## <a name="remarks"></a>解説

このクラスは、2 つのコンストラクター オーバーロードを定義 **&**`LPRECT`します。 最初のコンストラクターは、クラスの単一のデータ メンバー m_lpRectに参照引数のアドレス[を](#_u_rect__m_lprect)格納します。 ポインター コンストラクターの引数は、変換なしで直接格納されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="_u_rectm_lprect"></a><a name="_u_rect__m_lprect"></a>_U_RECT::m_lpRect

クラスは、パブリック`LPRECT`データ メンバーとして、コンストラクターのいずれかに渡される値を保持します。

```
LPRECT m_lpRect;
```

## <a name="_u_rect_u_rect"></a><a name="_u_rect___u_rect"></a>_U_RECT::_U_RECT

参照引数のアドレスは、クラスの単一のデータ メンバー [m_lpRect](#_u_rect__m_lprect)に格納されます。

```
_U_RECT(RECT& rc);
_U_RECT(LPRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*Rc*<br/>
`RECT` 参照。

*Lprect*<br/>
`RECT`ポインター。

### <a name="remarks"></a>解説

ポインター コンストラクターの引数は、変換なしで直接格納されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
