---
title: 抽出エラーのテスト | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc84277b654a79eebd38461c3ee83aefd533e4a8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="testing-for-extraction-errors"></a>抽出エラーのテスト

[エラー処理関数](../standard-library/output-file-stream-member-functions.md)に関する記事で説明されている出力エラー処理関数を、入力ストリームに適用します。 抽出時にエラーをテストすることは重要です。 次のようなステートメントを考えてみましょう。

```cpp
cin>> n;
```

`n` が符号付きの整数である場合、値が 32,767 (最大許容値。つまり MAX_INT) を超えるとストリームの `fail` ビットが設定され、`cin` オブジェクトは使用できなくなります。 これ以降の抽出ではすべて、値が格納されないまますぐに戻り値が返されます。

## <a name="see-also"></a>関連項目

[入力ストリーム](../standard-library/input-streams.md)<br/>
