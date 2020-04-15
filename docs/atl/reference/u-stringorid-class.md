---
title: _U_STRINGorIDクラス
ms.date: 11/04/2016
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
ms.openlocfilehash: 4e46ceec077b8daf8ef2a76110d2fc19dd39ae26
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325822"
---
# <a name="_u_stringorid-class"></a>_U_STRINGorIDクラス

この引数アダプター・クラスを使用すると、呼び出し元が MAKEINTRESOURCE マクロを使用して ID をストリングに変換しなくても、リソース名 (LPCTSTR) またはリソース ID (UINT) を関数に渡すことができます。

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
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|コンストラクターです。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|リソース識別子。|

## <a name="remarks"></a>解説

このクラスは、リソースの名前またはその ID である LPCTSTR[引数を受](/windows/win32/api/winuser/nf-winuser-loadiconw)け取る[、Windows リソース](/windows/win32/api/winbase/nf-winbase-findresourcea)管理 API のラッパーを実装するために設計されています。 [LoadMenu](/windows/win32/api/winuser/nf-winuser-loadmenuw)

このクラスは、2 つのコンストラクター オーバーロードを定義します。 UINT 引数は、MAKEINTRESOURCE マクロを使用して Windows リソース管理機能と互換性のあるリソース・タイプに変換され、その結果はクラスの単一データ・メンバー [m_lpstr](#_u_stringorid__m_lpstr)に保管されます。 LPCTSTR コンストラクタの引数は、変換なしで直接格納されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlwin.h

## <a name="_u_stringoridm_lpstr"></a><a name="_u_stringorid__m_lpstr"></a>_U_STRINGorID::m_lpstr

クラスは、パブリック LPCTSTR データ メンバーとして、そのコンストラクターのいずれかに渡される値を保持します。

```
LPCTSTR m_lpstr;
```

## <a name="_u_stringorid_u_stringorid"></a><a name="_u_stringorid___u_stringorid"></a>_U_STRINGorID::_U_STRINGorID

UINT コンストラクターは、MAKEINTRESOURCE マクロを使用して、その引数を Windows リソース管理機能と互換性のあるリソース型に変換し、その結果はクラスの単一のデータ メンバー [m_lpstr](#_u_stringorid__m_lpstr)に格納されます。

```
_U_STRINGorID(UINT nID);
_U_STRINGorID(LPCTSTR lpString);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
リソース ID。

*文字列*<br/>
リソース名。

### <a name="remarks"></a>解説

LPCTSTR コンストラクタの引数は、変換なしで直接格納されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
