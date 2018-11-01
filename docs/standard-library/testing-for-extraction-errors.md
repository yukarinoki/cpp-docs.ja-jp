---
title: 抽出エラーのテスト
ms.date: 11/04/2016
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
ms.openlocfilehash: 62d9c94f366ec666acf2179803c62e4a3ccd7e6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629230"
---
# <a name="testing-for-extraction-errors"></a>抽出エラーのテスト

[エラー処理関数](../standard-library/output-file-stream-member-functions.md)に関する記事で説明されている出力エラー処理関数を、入力ストリームに適用します。 抽出時にエラーをテストすることは重要です。 次のようなステートメントを考えてみましょう。

```cpp
cin>> n;
```

`n` が符号付きの整数である場合、値が 32,767 (最大許容値。つまり MAX_INT) を超えるとストリームの `fail` ビットが設定され、`cin` オブジェクトは使用できなくなります。 これ以降の抽出ではすべて、値が格納されないまますぐに戻り値が返されます。

## <a name="see-also"></a>関連項目

[入力ストリーム](../standard-library/input-streams.md)<br/>
