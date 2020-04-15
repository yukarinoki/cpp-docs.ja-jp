---
title: クラスを単純にスレッド化クラス
ms.date: 11/04/2016
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
ms.openlocfilehash: 4a3cce492db4db9f46aeb4efe738ee6a594ddcfc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327345"
---
# <a name="ccomsimplethreadallocator-class"></a>クラスを単純にスレッド化クラス

このクラスは、 クラス`CComAutoThreadModule`のスレッド選択を管理します。

## <a name="syntax"></a>構文

```
class CComSimpleThreadAllocator
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#getthread)|スレッドを選択します。|

## <a name="remarks"></a>解説

`CComSimpleThreadAllocator`のスレッドの選択[を管理します](../../atl/reference/ccomautothreadmodule-class.md)。 `CComSimpleThreadAllocator::GetThread`各スレッドを循環して、シーケンス内の次のスレッドを返すだけです。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccomsimplethreadallocatorgetthread"></a><a name="getthread"></a>をクリックします。

シーケンス内の次のスレッドを指定して、スレッドを選択します。

```
int GetThread(CComApartment* /* pApt */, int nThreads);
```

### <a name="parameters"></a>パラメーター

*プアプト*<br/>
ATL の既定の実装では使用されません。

*nスレッド*<br/>
EXE モジュール内のスレッドの最大数。

### <a name="return-value"></a>戻り値

0 と (*nThreads* - 1) の間の整数。 EXE モジュール内のスレッドの 1 つを識別します。

### <a name="remarks"></a>解説

オーバーライド`GetThread`して、異なる選択方法を提供したり *、pApt*パラメーターを使用したりできます。

`GetThread`によって呼び出[されます](../../atl/reference/ccomautothreadmodule-class.md#createinstance)。

## <a name="see-also"></a>関連項目

[コムアパートメント クラス](../../atl/reference/ccomapartment-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
