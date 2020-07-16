---
title: SyncLockWithStatusT クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT class
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT, constructor
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
ms.openlocfilehash: a111e0368ec6f4fcf8e89383b6261ad25ca6ebcf
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86403825"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT クラス

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename SyncTraits>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>パラメーター

*SyncTraits*<br/>
リソースの排他的な所有権を取得できる型。

## <a name="remarks"></a>解説

リソースの排他的な所有権を取得できる型を表します。

クラスは、 `SyncLockWithStatusT` [ミューテックス](mutex-class.md)クラスと[セマフォ](semaphore-class.md)クラスを実装するために使用されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                             | 説明
---------------------------------------------------------------- | --------------------------------------------------------------
[SyncLockWithStatusT:: SyncLockWithStatusT](#synclockwithstatust) | `SyncLockWithStatusT` クラスの新しいインスタンスを初期化します。

### <a name="protected-constructors"></a>プロテクト コンストラクター

名前                                                             | 説明
---------------------------------------------------------------- | --------------------------------------------------------------
[SyncLockWithStatusT:: SyncLockWithStatusT](#synclockwithstatust) | `SyncLockWithStatusT` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                         | 説明
-------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------
[SyncLockWithStatusT:: GetStatus](#getstatus) | 現在のオブジェクトの待機ステータスを取得し `SyncLockWithStatusT` ます。
[SyncLockWithStatusT:: IsLocked](#islocked)   | 現在のオブジェクトがリソースを所有しているかどうか、 `SyncLockWithStatusT` つまり、 `SyncLockWithStatusT` オブジェクトが*ロック*されているかどうかを示します。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                                    | 説明
--------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------
[SyncLockWithStatusT:: status_](#status) | 現在のオブジェクトに基づくオブジェクトに対するロック操作後の、基になる待機操作の結果を保持し `SyncLockWithStatusT` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper::D etails

## <a name="synclockwithstatustgetstatus"></a><a name="getstatus"></a>SyncLockWithStatusT:: GetStatus

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
DWORD GetStatus() const;
```

### <a name="return-value"></a>戻り値

`SyncLockWithStatusT`[ミューテックス](mutex-class.md)または[セマフォ](semaphore-class.md)など、クラスに基づくオブジェクトに対する待機操作の結果です。 ゼロ (0) は、待機操作がシグナル状態を返したことを示します。それ以外の場合は、タイムアウト値が経過したなどの別の状態が発生します。

### <a name="remarks"></a>解説

現在のオブジェクトの待機ステータスを取得し `SyncLockWithStatusT` ます。

GetStatus () 関数は、基になる[status_](#status)データメンバーの値を取得します。 クラスに基づくオブジェクトが `SyncLockWithStatusT` ロック操作を実行すると、オブジェクトは、オブジェクトが使用可能になるまで最初に待機します。 その待機操作の結果は、データメンバーに格納され `status_` ます。 データメンバーの有効な値は、 `status_` 待機操作の戻り値です。 詳細については、関数の戻り値を参照してください [`WaitForSingleObjectEx`](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobjectex) 。

## <a name="synclockwithstatustislocked"></a><a name="islocked"></a>SyncLockWithStatusT:: IsLocked

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
bool IsLocked() const;
```

### <a name="remarks"></a>解説

現在のオブジェクトがリソースを所有しているかどうか、 `SyncLockWithStatusT` つまり、 `SyncLockWithStatusT` オブジェクトが*ロック*されているかどうかを示します。

### <a name="return-value"></a>戻り値

**true** `SyncLockWithStatusT` オブジェクトがロックされている場合は true、それ以外の場合は**false**。

## <a name="synclockwithstatuststatus_"></a><a name="status"></a>SyncLockWithStatusT:: status_

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
DWORD status_;
```

### <a name="remarks"></a>解説

現在のオブジェクトに基づくオブジェクトに対するロック操作後の、基になる待機操作の結果を保持し `SyncLockWithStatusT` ます。

## <a name="synclockwithstatustsynclockwithstatust"></a><a name="synclockwithstatust"></a>SyncLockWithStatusT:: SyncLockWithStatusT

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
SyncLockWithStatusT(
   _Inout_ SyncLockWithStatusT&& other
);

explicit SyncLockWithStatusT(
   typename SyncTraits::Type sync,
   DWORD status
);
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
別のオブジェクトへの右辺値参照 `SyncLockWithStatusT` 。

*頻度*<br/>
別のオブジェクトへの参照 `SyncLockWithStatusT` 。

*status*<br/>
*他*のパラメーターまたは*同期*パラメーターの[status_](#status)データメンバーの値。

### <a name="remarks"></a>解説

`SyncLockWithStatusT` クラスの新しいインスタンスを初期化します。

最初のコンストラクターは、 `SyncLockWithStatusT` `SyncLockWithStatusT` *他の*パラメーターによって指定された別のオブジェクトから現在のオブジェクトを初期化し、もう一方のオブジェクトを無効にし `SyncLockWithStatusT` ます。 2番目のコンストラクターは `protected` で、現在の `SyncLockWithStatusT` オブジェクトを無効な状態に初期化します。
