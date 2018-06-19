---
title: 遅延読み込みした DLL に対するすべてのインポートの読み込み |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f054479a6681ba6de57690295fe3ce9f6c83696
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374373"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>遅延読み込みされた DLL に対するすべてのインポートの読み込み
**_ _Hrloadallimportsfordll** delayhlp.cpp で定義されて、関数で指定された DLL からすべてのインポートを読み込むようにリンカーに指示、 [/delayload](../../build/reference/delayload-delay-load-import.md)リンカー オプション。  
  
 すべてのインポートの読み込みを使用すると、コード内の 1 つの場所でエラー処理および例外処理のインポートに実際の呼び出しの周囲を使用する必要はありませんできます。 また、アプリケーションが失敗した場所部分的にインポートの読み込みに失敗したヘルパー コードの結果としてプロセスによって状況を回避できます。  
  
 呼び出す **_ _hrloadallimportsfordll**フック関数とエラーの動作は変わりません処理; を参照してください[エラー処理と通知](../../build/reference/error-handling-and-notification.md)詳細についてはします。  
  
 渡される DLL 名 **_ _hrloadallimportsfordll** DLL 自体の内部に格納されている名前と比較され、大文字小文字を区別します。  
  
 次の例を呼び出す方法を示します **_ _hrloadallimportsfordll**:  
  
```  
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {  
   printf ( "failed on snap load, exiting\n" );  
   exit(2);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)