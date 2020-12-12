---
description: '詳細情報: bad_target クラス'
title: bad_target クラス
ms.date: 11/04/2016
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
helpviewer_keywords:
- bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
ms.openlocfilehash: 0bade57ef06ee1ecf675d69531da918fc2a3510f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172246"
---
# <a name="bad_target-class"></a>bad_target クラス

このクラスは、実行する操作の無効なターゲットへのポインターがメッセージング ブロックに渡された場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class bad_target : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[bad_target](#ctor)|オーバーロードされます。 `bad_target` オブジェクトを構築します。|

## <a name="remarks"></a>解説

この例外は、通常、ターゲットが別のターゲット用に予約されているメッセージを使用しようとした場合や、保持していない予約を解除しようとした場合にスローされます。

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`bad_target`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="bad_target"></a><a name="ctor"></a> bad_target

`bad_target` オブジェクトを構築します。

```cpp
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)
