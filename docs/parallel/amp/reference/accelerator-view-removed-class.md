---
title: accelerator_view_removed クラス
ms.date: 11/04/2016
f1_keywords:
- accelerator_view_removed
- AMPRT/accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed:accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed:get_view_removed_reason
helpviewer_keywords:
- AMPRT/Concurrency::accelerator_view_removed:accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
ms.openlocfilehash: c51d05b098c395a498bc67d14061185c5d84ebb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462700"
---
# <a name="acceleratorviewremoved-class"></a>accelerator_view_removed クラス

基になる DirectX の呼び出しが Windows のタイムアウトの検出と回復機構が原因で失敗した場合にスローされる例外。

## <a name="syntax"></a>構文

```
class accelerator_view_removed : public runtime_exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[accelerator_view_removed コンス トラクター](#ctor)|`accelerator_view_removed` クラスの新しいインスタンスを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[get_view_removed_reason](#get_view_removed_reason)|原因を示す HRESULT エラー コードを返します、`accelerator_view`オブジェクトの削除。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>必要条件

**ヘッダー:** amprt.h

**名前空間:** Concurrency

## <a name="ctor"></a> accelerator_view_removed

新しいインスタンスを初期化、 [accelerator_view_removed](accelerator-view-removed-class.md)クラス。

### <a name="syntax"></a>構文

```
explicit accelerator_view_removed(
    const char * _Message,
    HRESULT _View_removed_reason ) throw();

explicit accelerator_view_removed(
    HRESULT _View_removed_reason ) throw();
```

### <a name="parameters"></a>パラメーター

*メッセージ (_m)*<br/>
エラーの説明。

*_View_removed_reason*<br/>
削除の原因を示す HRESULT エラー コード、`accelerator_view`オブジェクト。

### <a name="return-value"></a>戻り値

Accelerator_view_removed クラスの新しいインスタンス。

## <a name="get_view_removed_reason_method"></a> get_view_removed_reason

原因を示す HRESULT エラー コードを返します、`accelerator_view`オブジェクトの削除。

### <a name="syntax"></a>構文

```
HRESULT get_view_removed_reason() const throw();
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
