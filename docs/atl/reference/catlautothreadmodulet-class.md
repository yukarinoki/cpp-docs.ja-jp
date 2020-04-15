---
title: クラスを自動処理します。
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
ms.openlocfilehash: e7b7a327d7c47c4472b43ed58fbe9ad0556a7620
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321539"
---
# <a name="catlautothreadmodulet-class"></a>クラスを自動処理します。

このクラスは、スレッド プールのアパートメント モデル COM サーバーを実装するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T,
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
COM サーバーを実装するクラス。

*スレッドアロケーター*<br/>
スレッドの選択を管理するクラス。 既定値は[、CComSimple スレッドアロケーターです](../../atl/reference/ccomsimplethreadallocator-class.md)。

*dwWait*<br/>
タイムアウト間隔をミリ秒単位で指定します。 デフォルトは INFINITE で、メソッドのタイムアウト間隔が経過することはありません。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を取得します。](#getdefaultthreads)|この静的関数は、プロセッサの数に基づいて、EXE モジュールのスレッドの最大数を動的に計算して返します。|

## <a name="remarks"></a>解説

クラス[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)は、`CAtlAutoThreadModuleT`スレッド プール、アパートメント モデルの COM サーバーを実装するためにから派生します。 廃止されたクラス[を](../../atl/reference/ccomautothreadmodule-class.md)置き換えます。

> [!NOTE]
> 既定の*dwWait*値の INFINITE は DLL がアンロードされたときにデッドロックを発生させるため、このクラスは DLL で使用しないでください。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlAutoThreadModule`

`CAtlAutoThreadModuleT`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="catlautothreadmoduletgetdefaultthreads"></a><a name="getdefaultthreads"></a>を取得します。

この静的関数は、プロセッサの数に基づいて、EXE モジュールのスレッドの最大数を動的に計算して返します。

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>戻り値

EXE モジュールで作成されるスレッドの数。

### <a name="remarks"></a>解説

スレッド数を計算するために別のメソッドを使用する場合は、このメソッドをオーバーライドします。 デフォルトでは、スレッド数はプロセッサ数に基づいて行われます。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラス](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[モジュール クラス](../../atl/atl-module-classes.md)
