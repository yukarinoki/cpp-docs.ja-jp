---
title: '#エラー ディレクティブ (C/C++) |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#error'
dev_langs:
- C++
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 143733af9003442996d9f649825f45f93643f536
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078805"
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