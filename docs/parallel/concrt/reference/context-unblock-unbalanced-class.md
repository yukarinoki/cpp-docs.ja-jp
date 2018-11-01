---
title: context_unblock_unbalanced クラス
ms.date: 11/04/2016
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
ms.openlocfilehash: cc2ef970fa354da4abb7351cb4f1188451887552
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525928"
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

## <a name="requirements"></a>必要条件

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
