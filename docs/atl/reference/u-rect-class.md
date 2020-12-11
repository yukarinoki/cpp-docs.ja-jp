---
description: '詳細情報: _U_RECT クラス'
title: _U_RECT クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
ms.openlocfilehash: b3720107d1b64f930b4c64dff269de041d9b928c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157608"
---
# <a name="_u_rect-class"></a>_U_RECT クラス

この引数アダプタークラスを使用すると、ポインター `RECT` または参照を、ポインターの観点から実装された関数に渡すことができます。

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
|[_U_RECT:: _U_RECT](#_u_rect___u_rect)|コンストラクターです。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[_U_RECT:: m_lpRect](#_u_rect__m_lprect)|へのポインター `RECT` 。|

## <a name="remarks"></a>解説

クラスは、2つのコンストラクターオーバーロードを定義します。1つは **RECT&** 引数を受け取り、もう1つは引数を受け取り `LPRECT` ます。 1つ目のコンストラクターは、クラスの単一のデータメンバーである [m_lpRect](#_u_rect__m_lprect)に参照引数のアドレスを格納します。 ポインターコンストラクターへの引数は、変換せずに直接格納されます。

## <a name="requirements"></a>要件

**ヘッダー:** atlwin. h

## <a name="_u_rectm_lprect"></a><a name="_u_rect__m_lprect"></a> _U_RECT:: m_lpRect

クラスは、そのコンストラクターのいずれかに、パブリックデータメンバーとして渡された値を保持し `LPRECT` ます。

```
LPRECT m_lpRect;
```

## <a name="_u_rect_u_rect"></a><a name="_u_rect___u_rect"></a> _U_RECT:: _U_RECT

参照引数のアドレスは、クラスの単一のデータメンバーである [m_lpRect](#_u_rect__m_lprect)に格納されます。

```
_U_RECT(RECT& rc);
_U_RECT(LPRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*リターン*<br/>
`RECT` 参照。

*lpRect*<br/>
`RECT`ポインター。

### <a name="remarks"></a>解説

ポインターコンストラクターへの引数は、変換せずに直接格納されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
