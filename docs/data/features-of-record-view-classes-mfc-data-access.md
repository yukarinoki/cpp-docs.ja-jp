---
title: レコードの機能は、クラス (MFC データ アクセス) を表示 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b1c99b8b271b4948584d9bdb25c74518fe835573
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093221"
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>レコード ビュー クラスの機能 (MFC データ アクセス)

クラスを使用したフォーム ベースのデータ アクセス プログラミングを行うことができます[CFormView](../mfc/reference/cformview-class.md)が[CRecordView](../mfc/reference/crecordview-class.md)は通常より優れたクラスから派生します。 加え、`CFormView`機能、 `CRecordView`:  
  
- フォーム コントロールと関連付けられているレコード セット オブジェクトの間のダイアログ データ エクス (チェンジ DDX) を提供します。  
  
- 関連するレコード セット オブジェクト内のレコード間を移動するための Move First、Move Next、Move Previous、および最後に移動のコマンドを処理します。  
  
- 更新プログラムは、ユーザーが別のレコードに移動したときに、現在のレコードを変更します。  
  
ナビゲーションの詳細については、次を参照してください。[レコード ビュー: レコード ビュー内のナビゲーションのサポート](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)します。  
  
## <a name="see-also"></a>関連項目  

[レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)<br/>
[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)