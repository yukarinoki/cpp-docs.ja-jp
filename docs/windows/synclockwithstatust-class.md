---
title: SyncLockWithStatusT クラス |Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT class
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT, constructor
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b7e59631592cd0bf9d147110e1a72d27d4bc781e
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789086"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT クラス

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename SyncTraits>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>パラメーター

*SyncTraits*<br/>
排他的に使用できる型またはリソースの所有権を共有します。

## <a name="remarks"></a>Remarks

排他的に使用できる型を表すか、リソースの所有権を共有します。

`SyncLockWithStatusT`クラスが実装するために使用される、[ミュー テックス](../windows/mutex-class1.md)と[セマフォ](../windows/semaphore-class.md)クラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                             | 説明
---------------------------------------------------------------- | --------------------------------------------------------------
[Synclockwithstatust::synclockwithstatust](#synclockwithstatust) | `SyncLockWithStatusT` クラスの新しいインスタンスを初期化します。

### <a name="protected-constructors"></a>プロテクト コンストラクター

名前                                                             | 説明
---------------------------------------------------------------- | --------------------------------------------------------------
[Synclockwithstatust::synclockwithstatust](#synclockwithstatust) | `SyncLockWithStatusT` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                         | 説明
-------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------
[Synclockwithstatust::getstatus](#getstatus) | 現在の待機状態を取得`SyncLockWithStatusT`オブジェクト。
[Synclockwithstatust::islocked](#islocked)   | 示すかどうか、現在`SyncLockWithStatusT`リソースを所有するオブジェクトです。 つまり、`SyncLockWithStatusT`オブジェクトが*ロック*します。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                                    | 説明
--------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------
[Synclockwithstatust::status _](#status) | 基になる待機操作の結果を保持するオブジェクトのロック操作が現在に基づいて後`SyncLockWithStatusT`オブジェクト。

## <a name="inheritance-hierarchy"></a>継承階層

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="getstatus"></a>Synclockwithstatust::getstatus

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
DWORD GetStatus() const;
```

### <a name="return-value"></a>戻り値

基づくオブジェクトの待機操作の結果、`SyncLockWithStatusT`クラスなど、[ミュー テックス](../windows/mutex-class1.md)または[セマフォ](../windows/semaphore-class.md)します。 ゼロ (0) では、待機操作にはシグナルの状態が返されることを示しますそれ以外の場合、別の状態が発生しました、タイムアウト値が経過した場合など。

### <a name="remarks"></a>Remarks

現在の待機状態を取得`SyncLockWithStatusT`オブジェクト。

GetStatus() 関数は、基になる値を取得[status _](#status)データ メンバー。 基づくオブジェクト、`SyncLockWithStatusT`クラスは、ロック操作を実行、使用可能になるオブジェクトのオブジェクトが最初に待機します。 待機操作の結果は、`status_`データ メンバー。 可能な値、`status_`データ メンバーは、待機操作の戻り値。 詳細については、の戻り値を参照してください、 `WaitForSingleObjectEx()` MSDN ライブラリ内の関数。

## <a name="islocked"></a>Synclockwithstatust::islocked

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
bool IsLocked() const;
```

### <a name="remarks"></a>Remarks

示すかどうか、現在`SyncLockWithStatusT`リソースを所有するオブジェクトです。 つまり、`SyncLockWithStatusT`オブジェクトが*ロック*します。

### <a name="return-value"></a>戻り値

`true` 場合、`SyncLockWithStatusT`オブジェクトがロックされている場合はそれ以外の場合、`false`します。

## <a name="status"></a>Synclockwithstatust::status _

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
DWORD status_;
```

### <a name="remarks"></a>Remarks

基になる待機操作の結果を保持するオブジェクトのロック操作が現在に基づいて後`SyncLockWithStatusT`オブジェクト。

## <a name="synclockwithstatust"></a>Synclockwithstatust::synclockwithstatust

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

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

*other*<br/>
別の右辺値参照`SyncLockWithStatusT`オブジェクト。

*sync*<br/>
別の参照`SyncLockWithStatusT`オブジェクト。

*status*<br/>
値、 [status _](#status)のデータ メンバー、*他*パラメーターまたは*同期*パラメーター。

### <a name="remarks"></a>Remarks

`SyncLockWithStatusT` クラスの新しいインスタンスを初期化します。

最初のコンス トラクターは、現在`SyncLockWithStatusT`から別のオブジェクト`SyncLockWithStatusT`パラメーターで指定された*他*、し、もう一方を無効に`SyncLockWithStatusT`オブジェクト。 2 番目のコンス トラクターは`protected`、し、現在初期化`SyncLockWithStatusT`オブジェクトを無効な状態にします。
