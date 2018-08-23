---
title: マルチ スレッド プログラムの問題の回避 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], troubleshooting
- errors [C++], multithreaded programs
- threading [C++], troubleshooting
- troubleshooting [C++], multithreading
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49c5e624b437f39270fb880fe526d55e7ed83e5d
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2018
ms.locfileid: "42539048"
---
# <a name="avoiding-problem-areas-with-multithread-programs"></a>マルチスレッド プログラムの問題を回避する方法
いくつかの問題を作成する、リンク、またはマルチ スレッドの C プログラムの実行で発生する可能性があります。 いくつかの一般的な問題については、次の表で説明します。 (MFC の観点から詳細については、次を参照してください[マルチ スレッド: プログラミングのヒント](../parallel/multithreading-programming-tips.md)。)。  
  
|問題|考えられる原因|  
|-------------|--------------------|  
|プログラムによる保護違反を示すメッセージ ボックスが表示されます。|多くの Win32 プログラミング エラーには、保護違反が発生します。 保護違反の一般的な原因は、データ null ポインターへからの間接割り当てです。 属していないメモリにアクセスしようとして、プログラムでこの結果、ため、保護違反となります。<br /><br /> 保護違反の原因を検出する簡単な方法が、デバッグ情報でプログラムをコンパイルし、Visual C 環境でデバッガーを実行します。 保護違反が発生したときに、Windows デバッガーに制御を転送して、問題が発生した行にカーソルが配置されています。|  
|プログラムでは、さまざまなコンパイルとリンクのエラーを生成します。|コンパイラの警告レベルを最も高い値のいずれかに設定し、警告メッセージを heeding では、多くの潜在的な問題を解消できます。 レベル 3 または 4 レベルの警告レベル オプションを使用して、意図しないデータの変換や、不足している関数のプロトタイプの ANSI 以外の機能の使用を検出できます。|  
  
## <a name="see-also"></a>関連項目  

[C と Win32 を使用するマルチスレッド](../parallel/multithreading-with-c-and-win32.md)