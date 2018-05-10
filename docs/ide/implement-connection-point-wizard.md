---
title: 接続ポイント ウィザードを実装して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.impl.cp.overview
dev_langs:
- C++
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
ms.assetid: c117f6c6-30f0-4adb-82b4-b1f34e0f0fa8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef2f7efa92de3714170e403ea50b5f486c8367d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="implement-connection-point-wizard"></a>接続ポイントの実装ウィザード
このウィザードでは、COM オブジェクトのコネクション ポイントを実装します。 接続可能なオブジェクト (ソース) は、独自のインターフェイスまたは任意の発信インターフェイスの接続ポイントを公開できます。 Visual C と Windows 両方は、発信インターフェイスのタイプ ライブラリを提供します。 オブジェクト (つまり、シンク) 上のクライアントでは、各発信インターフェイスを実装できます。  
  
 詳細については、次を参照してください。 [ATL コネクション ポイント](../atl/atl-connection-points.md)です。  
  
 **使用可能なタイプ ライブラリ**  
 接続ポイントを実装できるインターフェイスの定義を含む使用可能なタイプ ライブラリを表示します。 使用するタイプ ライブラリを含むファイルを検索する、省略記号ボタンをクリックします。  
  
 **場所**  
 現在選択されているタイプ ライブラリの場所を表示、**使用可能なタイプ ライブラリ** ボックスの一覧です。  
  
 **インターフェイス**  
 現在選択されているタイプ ライブラリに定義が含まれているインターフェイスを表示、**使用可能なタイプ ライブラリ**ボックス。  
  
|転送ボタン|説明|  
|---------------------|-----------------|  
|**>**|追加、**接続ポイントを実装する**で現在選択されているインターフェイスの名前を一覧表示、**インターフェイス** ボックスの一覧です。|  
|**>>**|追加、**接続ポイントを実装する**で使用可能なすべてのインターフェイス名を一覧表示、**インターフェイス** ボックスの一覧です。|  
|**<**|現在選択されているインターフェイスの名前を削除、**接続ポイントを実装する** ボックスの一覧です。|  
|**<<**|削除のすべてのインターフェイス名で現在表示されている、**接続ポイントを実装する** ボックスの一覧です。|  
  
 **接続ポイントの実装**  
 実装する接続ポイントをクリックすると、インターフェイスの名前を表示**完了**です。  
  
## <a name="see-also"></a>関連項目  
 [接続ポイントを実装します。](../ide/implementing-a-connection-point-visual-cpp.md)