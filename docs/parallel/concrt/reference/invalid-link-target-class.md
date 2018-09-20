---
title: invalid_link_target クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_link_target
- CONCRT/concurrency::invalid_link_target
- CONCRT/concurrency::invalid_link_target::invalid_link_target
dev_langs:
- C++
helpviewer_keywords:
- invalid_link_target class
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 65937e1daee2bcd75300f5dc6b19c444ee542f64
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412614"
---
# <a name="invalidlinktarget-class"></a>invalid_link_target クラス

このクラスは、メッセージング ブロックの `link_target` メソッドが呼び出されたときに、そのメッセージング ブロックがターゲットにリンクできない場合にスローされる例外を表します。 この例外の原因としては、メッセージング ブロックのリンク数の上限を超えた場合、または特定のターゲットを同じソースに 2 回リンクしようとした場合があります。

## <a name="syntax"></a>構文

```
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

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> invalid_link_target

`invalid_link_target` オブジェクトを構築します。

```
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```

### <a name="parameters"></a>パラメーター

*メッセージ (_m)*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)

