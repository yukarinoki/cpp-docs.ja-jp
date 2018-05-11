---
title: '#エラー ディレクティブ (C/C++) |Microsoft ドキュメント'
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
ms.openlocfilehash: ba4f0e06798bc6419f8db0471f19588039eb679a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="error-directive-cc"></a>#error ディレクティブ (C/C++)
`#error` ディレクティブは、コンパイル時にユーザー指定のエラー メッセージを出力して、コンパイルを終了します。  
  
## <a name="syntax"></a>構文  
  
```  
#errortoken-string  
```  
  
## <a name="remarks"></a>コメント  
 このディレクティブを出力するエラー メッセージには、*トークン文字列*パラメーター。 `token-string` パラメーターは、マクロ展開の対象になりません。 このディレクティブは、プリプロセス時にプログラムの不整合や制約の違反を開発者に通知するために最も役立ちます。 次の例は、プリプロセス中のエラーの処理を示しています。  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## <a name="see-also"></a>関連項目  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)