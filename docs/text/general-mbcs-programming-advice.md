---
title: 一般的な MBCS プログラミングにおけるアドバイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], dialog box fonts
- MS Shell Dlg
- MBCS [C++], programming
- dialog boxes [C++], fonts
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab2b67c82a04a0c355761ec6572a9718d03c4666
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855800"
---
# <a name="general-mbcs-programming-advice"></a>MBCS プログラミングにおける一般的なアドバイス
次のヒントを使用します。  
  
-   柔軟性を高める場合など、実行時のマクロを使用して`_tcschr`と`_tcscpy`可能な場合です。 詳細については、次を参照してください。 [Tchar.h における汎用テキスト マッピング](../text/generic-text-mappings-in-tchar-h.md)です。  
  
-   C ランタイムを使用して`_getmbcp`を現在のコード ページに関する情報を取得します。  
  
-   文字列リソースを再利用しません。 言語によっては、ターゲットを指定する文字列に変換するときに、異なる意味があります。 たとえば、"File"で、アプリケーションのメイン メニューは、文字列"File" ダイアログ ボックスから異なる方法で変換可能性があります。 同じ名前の 2 つ以上の文字列を使用する必要がある場合は、ごとに異なる文字列 Id を使用します。  
  
-   Mbcs のオペレーティング システム、アプリケーションが実行されているかどうかを検索する場合があります。 これを行うプログラムの起動時にフラグを設定します。API 呼び出しに依存しません。  
  
-   ダイアログ ボックスをデザインする場合に、約 30% を許可する MBCS 変換用の静的テキスト コントロールの末尾に余分なスペースです。  
  
-   必ず、アプリケーションのフォントを選択するときに一部のフォントはすべてのシステムで利用できないためです。  
  
-   ダイアログ ボックスのフォントを選択するを使用して[MS Shell Dlg](http://msdn.microsoft.com/library/windows/desktop/dd374112) MS Sans Serif や「helvetica」代わりにします。 MS Shell Dlg は適切なフォントに、ダイアログ ボックスを作成する前に、システムによって置換されます。 MS Shell Dlg を使用して、このフォントに対処するオペレーティング システムで変更が自動的に使用できることをによりします。 (MFC 置換 MS Shell Dlg DEFAULT_GUI_FONT または Windows 95、Windows 98、および Windows NT 4 で、システム フォントでこれらのシステムは MS Shell Dlg が正しく処理されないためです。)  
  
-   アプリケーションを設計するときに、どの言語で文字列をローカライズすることができますを決定します。 不明な場合に、すべての文字列をローカライズすることを想定しています。 そのため、混在させないでくださいローカライズ可能な文字列にすることはできません。  
  
## <a name="see-also"></a>関連項目  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [ポインターのインクリメントとデクリメント](../text/incrementing-and-decrementing-pointers.md)