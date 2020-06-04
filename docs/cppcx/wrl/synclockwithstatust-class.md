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
ms.openlocfilehash: 77bcb8336e4650de7ed01a067fa1bdd7ec0ba3e8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374263"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT クラス

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename SyncTraits>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>パラメーター

*同期トレイト*<br/>
リソースの排他的または共有所有権を取得できる型。

## <a name="remarks"></a>解説

リソースの排他的または共有所有権を取得できる型を表します。

この`SyncLockWithStatusT`クラスは、[ミューテックス](mutex-class.md)クラスと[セマフォ](semaphore-class.md)クラスを実装するために使用されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                             | 説明
---------------------------------------------------------------- | --------------------------------------------------------------
[ステータスを同期します。::同期します。](#synclockwithstatust) | `SyncLockWithStatusT` クラスの新しいインスタンスを初期化します。

### <a name="protected-constructors"></a>プロテクト コンストラクター

名前                                                             | 説明
---------------------------------------------------------------- | --------------------------------------------------------------
[ステータスを同期します。::同期します。](#synclockwithstatust) | `SyncLockWithStatusT` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                         | 説明
-------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------
[ステータスを取得します。](#getstatus) | 現在`SyncLockWithStatusT`のオブジェクトの待機状態を取得します。
[ステータスTと同期::IsLocked](#islocked)   | 現在`SyncLockWithStatusT`のオブジェクトがリソースを所有しているかどうかを示します。つまり、オブジェクトは`SyncLockWithStatusT`*ロックされています*。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                                    | 説明
--------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------
[ステータスを同期::status_](#status) | 現在`SyncLockWithStatusT`のオブジェクトに基づくオブジェクトのロック操作後に、基になる待機操作の結果を保持します。

## <a name="inheritance-hierarchy"></a>継承階層

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー::D

## <a name="synclockwithstatustgetstatus"></a><a name="getstatus"></a>ステータスを取得します。

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
DWORD GetStatus() const;
```

### <a name="return-value"></a>戻り値

`SyncLockWithStatusT`[クラス](mutex-class.md)に基づくオブジェクトに対する待機操作の結果[です。](semaphore-class.md) ゼロ (0) は、待機操作がシグナル状態を返したことを示します。それ以外の場合は、タイムアウト値が経過したなどの別の状態が発生しました。

### <a name="remarks"></a>解説

現在`SyncLockWithStatusT`のオブジェクトの待機状態を取得します。

GetStatus() 関数は、基になる[status_](#status)データ メンバーの値を取得します。 クラスに基づくオブジェクトが`SyncLockWithStatusT`ロック操作を実行すると、オブジェクトはまずオブジェクトが使用可能になるまで待機します。 その待機操作の結果は、データ メンバー`status_`に格納されます。 データ メンバーの値`status_`は、待機操作の戻り値です。 詳細については、MSDN ライブラリの関数の`WaitForSingleObjectEx()`戻り値を参照してください。

## <a name="synclockwithstatustislocked"></a><a name="islocked"></a>ステータスTと同期::IsLocked

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
bool IsLocked() const;
```

### <a name="remarks"></a>解説

現在`SyncLockWithStatusT`のオブジェクトがリソースを所有しているかどうかを示します。つまり、オブジェクトは`SyncLockWithStatusT`*ロックされています*。

### <a name="return-value"></a>戻り値

オブジェクトがロック`SyncLockWithStatusT`されている場合は true、ロックされている場合は**true。** それ以外の場合**は false。**

## <a name="synclockwithstatuststatus_"></a><a name="status"></a>ステータスを同期::status_

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
DWORD status_;
```

### <a name="remarks"></a>解説

現在`SyncLockWithStatusT`のオブジェクトに基づくオブジェクトのロック操作後に、基になる待機操作の結果を保持します。

## <a name="synclockwithstatustsynclockwithstatust"></a><a name="synclockwithstatust"></a>ステータスを同期します。::同期します。

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

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

*他*<br/>
別`SyncLockWithStatusT`のオブジェクトへの右辺値参照。

*同期*<br/>
別`SyncLockWithStatusT`のオブジェクトへの参照。

*status*<br/>
*他*のパラメーターまたは*同期*パラメーターの[status_](#status)データ メンバーの値。

### <a name="remarks"></a>解説

`SyncLockWithStatusT` クラスの新しいインスタンスを初期化します。

最初のコンストラクターは、パラメーター `SyncLockWithStatusT` *other*で指定された別の`SyncLockWithStatusT`オブジェクトから現在のオブジェクトを初期化し`SyncLockWithStatusT`、その後、そのオブジェクトを無効にします。 2 番目の`protected`コンストラクターは で、現在`SyncLockWithStatusT`のオブジェクトを無効な状態に初期化します。
