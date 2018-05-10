---
title: -Fi (出力ファイル名のプリプロセス) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fi
dev_langs:
- C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e7fe5ffbb8a6ccdd5ef02d2cf3feb6b94d48233
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (出力ファイル名のプリプロセス)
出力ファイルの名前を指定、 [/P (プリプロセス出力ファイルへの)](../../build/reference/p-preprocess-to-a-file.md)コンパイラ オプションは、プリプロセス済みの出力を書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
/Fipathname  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`pathname`|によって生成される出力ファイルのパスと名前、 **/P**コンパイラ オプション。|  
  
## <a name="remarks"></a>コメント  
 使用して、 **/Fi**コンパイラ オプションと組み合わせて、 **/P**コンパイラ オプション。  
  
 パスのみを指定する場合、`pathname`プリプロセス済みの出力ファイルの基本名とパラメーター、ソース ファイルのベース名を使用します。 `pathname`パラメーターでは、特定のファイル名拡張子は必要ありません。 ただし、".i"の拡張機能は、ファイル名拡張子が指定されていない場合に使用されます。  
  
## <a name="example"></a>例  
 次のコマンド ライン PROGRAM.cpp を前処理し、コメントを保持、追加[#line](../../preprocessor/hash-line-directive-c-cpp.md)ディレクティブは、その結果を MYPROCESS.i ファイルに書き込みます。  
  
```  
CL /P /FiMYPROCESS.I PROGRAM.CPP  
```  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [/P (ファイルへのプリプロセス)](../../build/reference/p-preprocess-to-a-file.md)   
 [パス名の指定](../../build/reference/specifying-the-pathname.md)