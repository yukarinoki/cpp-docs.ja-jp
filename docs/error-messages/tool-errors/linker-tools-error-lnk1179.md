---
title: リンカ ツール エラー LNK1179 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1179
dev_langs:
- C++
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72a531397c3c101fbff937f293f772c5f6778523
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300216"
---
# <a name="linker-tools-error-lnk1179"></a>リンカ ツール エラー LNK1179
ファイルが無効か破損しています: COMDAT 'filename' を複製します。  
  
 オブジェクト モジュールには、同じ名前の 2 つ以上の Comdat が含まれています。  
  
 使用してこのエラーは発生する[/H](../../build/reference/h-restrict-length-of-external-names.md)、外部名の長さを制限して[/Gy](../../build/reference/gy-enable-function-level-linking.md)Comdat に関数をパッケージ化します。  
  
## <a name="example"></a>例  
 次のコードに`function1`と`function2`が最初の 8 文字と一致します。 コンパイルする **/Gy**と **/H8**リンク エラーが生成されます。  
  
```  
void function1(void);  
void function2(void);  
  
int main() {  
    function1();  
    function2();  
}  
  
void function1(void) {}  
void function2(void) {}  
```