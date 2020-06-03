---
title: _U_MENUorIDクラス
ms.date: 11/04/2016
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
ms.openlocfilehash: 419c9e79178db12efe278838ec8630e04ac3c461
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325836"
---
# <a name="_u_menuorid-class"></a>_U_MENUorIDクラス

このクラスは、 および`CreateWindow``CreateWindowEx`のラッパーを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class _U_MENUorID
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|コンストラクターです。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|メニューへのハンドル。|

## <a name="remarks"></a>解説

この引数アダプター・クラスを使用すると、呼び出し元の部分に明示的なキャストを行わずに、ID (UINT) またはメニュー・ハンドル (HMENUS) を関数に渡すことができます。

このクラスは、Windows API のラッパーを実装するために設計されています, 特に[CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww)と[CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)関数, どちらも、メニュー ハンドルではなく、子ウィンドウ識別子 (UINT) である可能性がある HMENU 引数を受け入れます。 たとえば、このクラスを[CWindowImpl::Create](cwindowimpl-class.md#create)のパラメーターとして使用していることがわかります。

このクラスは 2 つのコンストラクター オーバーロードを定義します。 UINT 引数は、コンストラクタの HMENU にキャストされ、その結果はクラスの単一のデータ メンバ[m_hMenu](#_u_menuorid__m_hmenu)に格納されます。 HMENU コンストラクタの引数は、変換なしで直接格納されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="_u_menuoridm_hmenu"></a><a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu

クラスは、パブリック HMENU データ メンバーとして、そのコンストラクターのいずれかに渡される値を保持します。

```
HMENU m_hMenu;
```

## <a name="_u_menuorid_u_menuorid"></a><a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID

UINT 引数は、コンストラクタの HMENU にキャストされ、その結果はクラスの単一のデータ メンバ[m_hMenu](#_u_menuorid__m_hmenu)に格納されます。

```
_U_MENUorID(UINT nID);
_U_MENUorID(HMENU hMenu);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
子ウィンドウ識別子。

*Hmenu*<br/>
メニュー ハンドル。

### <a name="remarks"></a>解説

HMENU コンストラクタの引数は、変換なしで直接格納されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
