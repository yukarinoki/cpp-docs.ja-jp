---
description: '詳細情報: CAtlAutoThreadModuleT クラス'
title: CAtlAutoThreadModuleT クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
ms.openlocfilehash: ad55c78488567c12477c427b99a527b8154ddd22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158414"
---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT クラス

このクラスは、スレッドプールされたアパートメントモデル COM サーバーを実装するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```cpp
template <class T,
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```

### <a name="parameters"></a>パラメーター

*T*<br/>
COM サーバーを実装するクラス。

*ThreadAllocator*<br/>
スレッド選択を管理するクラス。 既定値は [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)です。

*dwWait*<br/>
タイムアウト間隔をミリ秒単位で指定します。 既定値は無限です。これは、メソッドのタイムアウト間隔が経過しないことを意味します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|この静的関数は、プロセッサの数に基づいて、実行可能モジュールのスレッドの最大数を動的に計算して返します。|

## <a name="remarks"></a>解説

[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)クラスは、 `CAtlAutoThreadModuleT` スレッドプールされたアパートメントモデルの COM サーバーを実装するためにから派生します。 互換性のために残されているクラス [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)を置き換えます。

> [!NOTE]
> このクラスは DLL では使用しないでください。既定の *Dwwait* 値は無限であるため、dll がアンロードされるとデッドロックが発生します。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlAutoThreadModule`

`CAtlAutoThreadModuleT`

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="catlautothreadmoduletgetdefaultthreads"></a><a name="getdefaultthreads"></a> CAtlAutoThreadModuleT::GetDefaultThreads

この静的関数は、プロセッサの数に基づいて、実行可能モジュールのスレッドの最大数を動的に計算して返します。

```cpp
static int GetDefaultThreads();
```

### <a name="return-value"></a>戻り値

EXE モジュールに作成されるスレッドの数。

### <a name="remarks"></a>解説

スレッド数を計算するために別のメソッドを使用する場合は、このメソッドをオーバーライドします。 既定では、スレッドの数はプロセッサの数に基づいています。

## <a name="see-also"></a>関連項目

[IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[モジュールクラス](../../atl/atl-module-classes.md)
