---
title: _callnewh
ms.date: 4/2/2020
api_name:
- _callnewh
- _o__callnewh
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _callnewh
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
ms.openlocfilehash: 3990d4b15c25cfd6c753c2b1d44c112971ff59af
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918798"
---
# <a name="_callnewh"></a>_callnewh

現在インストールされている*新しいハンドラー*を呼び出します。

## <a name="syntax"></a>構文

```cpp
int _callnewh(
   size_t size
   )
```

### <a name="parameters"></a>パラメーター

*size*<br/>
[new 演算子](../../cpp/new-operator-cpp.md)が割り当てようとしたメモリの量。

## <a name="return-value"></a>戻り値

|値|説明|
|-----------|-----------------|
|0|エラー: 新しいハンドラーがインストールされていないか、新しいハンドラーがアクティブになっていません。|
|1|成功: 新しいハンドラーがインストールされ、アクティブになっています。 メモリ割り当てを再試行できます。|

## <a name="exceptions"></a>例外

*新しいハンドラー*が見つからない場合、[bad_alloc](../../standard-library/bad-alloc-class.md) をスローします。

## <a name="remarks"></a>解説

*新しいハンドラー*は、[new 演算子](../../cpp/new-operator-cpp.md)がメモリの割り当てに失敗した場合に呼び出されます。 新しいハンドラーは、後続の割り当てが成功するようにメモリを解放するなど、適切な処理を開始する場合があります。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|_callnewh|internal.h|

## <a name="see-also"></a>関連項目

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>
