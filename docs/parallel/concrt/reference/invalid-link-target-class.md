---
description: '詳細情報: invalid_link_target クラス'
title: invalid_link_target クラス
ms.date: 11/04/2016
f1_keywords:
- invalid_link_target
- CONCRT/concurrency::invalid_link_target
- CONCRT/concurrency::invalid_link_target::invalid_link_target
helpviewer_keywords:
- invalid_link_target class
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
ms.openlocfilehash: d080886c3aab0ecc120d4ce13f5f75f2eecfea8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334581"
---
# <a name="invalid_link_target-class"></a>invalid_link_target クラス

このクラスは、メッセージング ブロックの `link_target` メソッドが呼び出されたときに、そのメッセージング ブロックがターゲットにリンクできない場合にスローされる例外を表します。 この例外の原因としては、メッセージング ブロックのリンク数の上限を超えた場合、または特定のターゲットを同じソースに 2 回リンクしようとした場合があります。

## <a name="syntax"></a>構文

```cpp
class invalid_link_target : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[invalid_link_target](#ctor)|オーバーロードされます。 `invalid_link_target` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`invalid_link_target`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="invalid_link_target"></a><a name="ctor"></a> invalid_link_target

`invalid_link_target` オブジェクトを構築します。

```cpp
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)
