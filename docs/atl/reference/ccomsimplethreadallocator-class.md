---
description: '詳細情報: CComSimpleThreadAllocator クラス'
title: CComSimpleThreadAllocator クラス
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
ms.openlocfilehash: 5925707ecd459475d9e9002af76fb76dd9cf9d38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142188"
---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator クラス

このクラスは、クラスのスレッド選択を管理 `CComAutoThreadModule` します。

## <a name="syntax"></a>構文

```
class CComSimpleThreadAllocator
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComSimpleThreadAllocator:: GetThread](#getthread)|スレッドを選択します。|

## <a name="remarks"></a>解説

`CComSimpleThreadAllocator`[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)のスレッドの選択を管理します。 `CComSimpleThreadAllocator::GetThread` は、各スレッドを順番に実行し、シーケンス内の次のスレッドを返すだけです。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="ccomsimplethreadallocatorgetthread"></a><a name="getthread"></a> CComSimpleThreadAllocator:: GetThread

シーケンス内の次のスレッドを指定することによって、スレッドを選択します。

```
int GetThread(CComApartment* /* pApt */, int nThreads);
```

### <a name="parameters"></a>パラメーター

*pApt*<br/>
ATL の既定の実装では使用されません。

*nThreads*<br/>
EXE モジュール内のスレッドの最大数。

### <a name="return-value"></a>戻り値

0から (*nThreads* -1) までの整数。 EXE モジュール内のスレッドの1つを識別します。

### <a name="remarks"></a>解説

をオーバーライドし `GetThread` て、別の選択方法を指定したり、 *pApt* パラメーターを使用したりすることができます。

`GetThread` は [CComAutoThreadModule:: CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance)によって呼び出されます。

## <a name="see-also"></a>関連項目

[CComApartment クラス](../../atl/reference/ccomapartment-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
