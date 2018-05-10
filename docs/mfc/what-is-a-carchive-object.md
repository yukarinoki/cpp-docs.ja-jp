---
title: CArchive オブジェクトとは |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55b97843a8aeb2599d2bdf34458b362fc5899368
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="what-is-a-carchive-object"></a>CArchive オブジェクトとは
A`CArchive`オブジェクトをシリアル化可能なオブジェクトの読み取りまたは書き込み用タイプ セーフ バッファリング メカニズムを提供する、`CFile`オブジェクト。 通常、`CFile`オブジェクトは、ディスク ファイルを表します。 ただし、メモリ ファイルにすることができますも (`CSharedFile`オブジェクト)、おそらく、クリップボードを表すです。  
  
 指定された`CArchive`オブジェクトのいずれかのストア (書き込みます、シリアル化) データまたは読み込みます (読み取り、逆シリアル化) は、データ両方です。 有効期間、`CArchive`オブジェクトは、ファイルへの書き込みまたはファイルからオブジェクトを読み取るには 1 つのパススルーに制限されます。 したがって、2 つの連続的に作成された`CArchive`オブジェクトがデータをファイルにシリアル化し、ファイルから逆シリアル化に必要です。  
  
 アーカイブがアタッチ アーカイブは、ファイルにオブジェクトを格納するとき、`CRuntimeClass`オブジェクト名。 別のアーカイブは、ファイルからオブジェクトをメモリに読み込むときに、 `CObject`-派生オブジェクトは動的に再構築に基づく、`CRuntimeClass`オブジェクト。 指定したオブジェクトにはファイルを格納するアーカイブで、ファイルに書き込むと複数回参照できます。 読み込みを行うアーカイブ、ただしはオブジェクトの再構築、1 回だけです。 詳細については、アーカイブのアタッチ、`CRuntimeClass`については、オブジェクトや再構築、他の複数の参照を行うに記載されて[テクニカル ノート 2:](../mfc/tn002-persistent-object-data-format.md)です。  
  
 データがアーカイブにシリアル化されると、バッファーがいっぱいになるまで、アーカイブ データが蓄積されます。 アーカイブするには、そのバッファーに出力、`CFile`によって指されるオブジェクト、`CArchive`オブジェクト。 同様に、アーカイブからデータを読み取り、データの読み取り、バッファーをファイルから、バッファーから逆シリアル化されたオブジェクトにします。 このバッファー処理すると、ハード ディスクは物理的に読み込まれる、ため、アプリケーションのパフォーマンスが向上する回数が減少します。  
  
## <a name="see-also"></a>関連項目  
 [シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)

