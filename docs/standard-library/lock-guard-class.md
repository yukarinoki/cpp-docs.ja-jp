---
title: lock_guard クラス
ms.date: 11/04/2016
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
ms.openlocfilehash: 989c1e368e95fc0009f0c3f1c71af0bdba20609d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351715"
---
# <a name="lock_guard-class"></a>lock_guard クラス

オブジェクトを作成し、そのデストラクタ―が `mutex` のロックを解除するためにインスタンス化できるテンプレートを表します。

## <a name="syntax"></a>構文

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>解説

テンプレート引数 `Mutex` には *mutex 型*を指定する必要があります。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`lock_guard::mutex_type`|テンプレート引数 `Mutex` のシノニム。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[lock_guard](#lock_guard)|`lock_guard` オブジェクトを構築します。|
|[lock_guard::~lock_guard デストラクター](#dtorlock_guard_destructor)|コンストラクターに渡された `mutex` をロック解除します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<ミューテックス>

**名前空間:** std

## <a name="lock_guardlock_guard-constructor"></a><a name="lock_guard"></a>lock_guard::lock_guardコンストラクタ

`lock_guard` オブジェクトを構築します。

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>パラメーター

*Mtx*\
*ミューテックス型*オブジェクト。

### <a name="remarks"></a>解説

最初のコンストラクターは型`lock_guard`のオブジェクトを構築し *、Mtx*をロックします。 *Mtx*が再帰ミューテックスでない場合、このコンストラクターが呼び出されたときにロックを解除する必要があります。

2 番目のコンストラクターは*Mtx*をロックしません。 このコンストラクタが呼び出されたときに*は、Mtx*をロックする必要があります。 このコンストラクターでは例外はスローされません。

## <a name="lock_guardlock_guard-destructor"></a><a name="dtorlock_guard_destructor"></a>lock_guard:~lock_guardデストラクタ

コンストラクターに渡された `mutex` をロック解除します。

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>解説

デストラクターの実行時に `mutex` が存在しない場合の動作は未定義です。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<ミューテックス>](../standard-library/mutex.md)
