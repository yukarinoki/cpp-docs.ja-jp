---
title: context_unblock_unbalanced クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
dev_langs:
- C++
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8cd35b53db37d51a9feec567fe66c53b1381b4d9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431334"
---
# <a name="contextunblockunbalanced-class"></a>context_unblock_unbalanced クラス

このクラスは、`Block` オブジェクトの `Unblock` メソッドと `Context` メソッドの呼び出しが正しく対になっていない場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|オーバーロードされます。 `context_unblock_unbalanced` オブジェクトを構築します。|

## <a name="remarks"></a>Remarks

呼び出し、`Block`と`Unblock`のメソッドを`Context`オブジェクトのペアを正しく常にする必要があります。 同時実行ランタイムは、操作を任意の順序で実行できます。 呼び出しなど`Block`への呼び出しを続けて`Unblock`、またはその逆です。 たとえば、2 つの呼び出しの場合、この例外がスローされます、`Unblock`メソッドで発生した行で、`Context`ブロックされていないオブジェクト。

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>要件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> context_unblock_unbalanced

`context_unblock_unbalanced` オブジェクトを構築します。

```
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>パラメーター

*メッセージ (_m)*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
