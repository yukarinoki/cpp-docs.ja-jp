---
title: scheduler_resource_allocation_error クラス
ms.date: 11/04/2016
f1_keywords:
- scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::get_error_code
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
ms.openlocfilehash: 7f7254306253aabc33f46694f3da16734e6efccf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160053"
---
# <a name="schedulerresourceallocationerror-class"></a>scheduler_resource_allocation_error クラス

このクラスは、同時実行ランタイムでクリティカル リソースを取得できないためにスローされる例外を表します。

## <a name="syntax"></a>構文

```
class scheduler_resource_allocation_error : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[scheduler_resource_allocation_error](#ctor)|オーバーロードされます。 `scheduler_resource_allocation_error` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[get_error_code](#get_error_code)|例外の原因となったエラー コードを返します。|

## <a name="remarks"></a>Remarks

同時実行ランタイムの内部からオペレーティング システムへの呼び出しが失敗した場合、この例外はスロー通常。 Win32 メソッドの呼び出しから返されるエラー コード`GetLastError`型の値に変換されます`HRESULT`を使用して取得できると、`get_error_code`メソッド。

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`scheduler_resource_allocation_error`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="get_error_code"></a> get_error_code

例外の原因となったエラー コードを返します。

```
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>戻り値

`HRESULT`例外の原因となったエラーの値。

##  <a name="ctor"></a> scheduler_resource_allocation_error

`scheduler_resource_allocation_error` オブジェクトを構築します。

```
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

*_Hresult*<br/>
`HRESULT`例外の原因となったエラーの値。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
