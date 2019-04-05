---
title: '#エラー ディレクティブ (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
ms.openlocfilehash: dc229a8eae6938cba32787ecbec6a5aa6a17ab47
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037845"
---
# <a name="error-directive-cc"></a>#error ディレクティブ (C/C++)
**#Error**ディレクティブはコンパイル時にユーザーが指定したエラー メッセージを出力して、コンパイルを終了します。

## <a name="syntax"></a>構文

```
#errortoken-string
```

## <a name="remarks"></a>Remarks

このディレクティブが生成されるエラー メッセージが含まれています、*トークン文字列*パラメーター。 *トークン文字列*パラメーター、マクロの展開対象になりません。 このディレクティブは、プリプロセス時にプログラムの不整合や制約の違反を開発者に通知するために最も役立ちます。 次の例は、プリプロセス中のエラーの処理を示しています。

```
#if !defined(__cplusplus)
#error C++ compiler required.
#endif
```

## <a name="see-also"></a>関連項目

[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)