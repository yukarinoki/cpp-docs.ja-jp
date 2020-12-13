---
description: '詳細情報: _U_STRINGorID クラス'
title: _U_STRINGorID クラス
ms.date: 11/04/2016
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
ms.openlocfilehash: bbbf3d32e86d035344ba8d3dcd60c4ebe66d9c3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138763"
---
# <a name="_u_stringorid-class"></a>_U_STRINGorID クラス

この引数アダプタークラスを使用すると、リソース名 (LPCTSTRs) またはリソース Id (UINTs) を関数に渡すことができます。呼び出し元は、MAKEINTRESOURCE マクロを使用して、ID を文字列に変換する必要はありません。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class _U_STRINGorID
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[_U_STRINGorID:: _U_STRINGorID](#_u_stringorid___u_stringorid)|コンストラクターです。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[_U_STRINGorID:: m_lpstr](#_u_stringorid__m_lpstr)|リソース識別子。|

## <a name="remarks"></a>解説

このクラスは、 [Findresource](/windows/win32/api/winbase/nf-winbase-findresourcea)、 [Loadicon](/windows/win32/api/winuser/nf-winuser-loadiconw)、 [loadicon](/windows/win32/api/winuser/nf-winuser-loadmenuw) などの Windows リソース管理 API にラッパーを実装するように設計されています。これらの関数は、リソースの名前または ID のいずれかである可能性がある LPCTSTR 引数を受け取ります。

クラスは、2つのコンストラクターオーバーロードを定義します。1つは LPCTSTR 引数を受け取り、もう1つは UINT 引数を受け取ります。 UINT 引数は、MAKEINTRESOURCE マクロと、クラスの単一のデータメンバーに格納された結果 [m_lpstr](#_u_stringorid__m_lpstr)を使用して、Windows リソース管理関数と互換性のあるリソースの種類に変換されます。 LPCTSTR コンストラクターの引数は、変換せずに直接格納されます。

## <a name="requirements"></a>要件

**ヘッダー:** atlwin. h

## <a name="_u_stringoridm_lpstr"></a><a name="_u_stringorid__m_lpstr"></a> _U_STRINGorID:: m_lpstr

クラスは、コンストラクターのいずれかに渡された値をパブリック LPCTSTR データメンバーとして保持します。

```
LPCTSTR m_lpstr;
```

## <a name="_u_stringorid_u_stringorid"></a><a name="_u_stringorid___u_stringorid"></a> _U_STRINGorID:: _U_STRINGorID

UINT コンストラクターは、MAKEINTRESOURCE マクロを使用して、引数を Windows リソース管理関数と互換性のあるリソースの種類に変換します。結果は、クラスの単一のデータメンバーである [m_lpstr](#_u_stringorid__m_lpstr)に格納されます。

```
_U_STRINGorID(UINT nID);
_U_STRINGorID(LPCTSTR lpString);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
リソース ID。

*lpString*<br/>
リソース名。

### <a name="remarks"></a>解説

LPCTSTR コンストラクターの引数は、変換せずに直接格納されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
