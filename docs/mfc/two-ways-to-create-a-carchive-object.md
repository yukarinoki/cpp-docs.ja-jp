---
title: CArchive オブジェクトを作成する方法は 2 |Microsoft ドキュメント
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
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87abaa5a3564c61a6944e0cc31e81375f92a3a80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="two-ways-to-create-a-carchive-object"></a>CArchive オブジェクトを作成する 2 つの方法
作成する方法を次の 2 つが、`CArchive`オブジェクト。  
  
-   [フレームワークによって CArchive オブジェクトの暗黙的な作成](#_core_implicit_creation_of_a_carchive_object_via_the_framework)  
  
-   [CArchive オブジェクトの明示的な作成](#_core_explicit_creation_of_a_carchive_object)  
  
##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> フレームワークによって CArchive オブジェクトの暗黙的な作成  
 最も一般的では、簡単な方法は、フレームワークには、`CArchive`保存、名前を付けて保存および開くコマンド ファイル メニューで、ドキュメントのオブジェクト。  
  
 フレームワークが、アプリケーションのユーザーがファイル メニューから 名前を付けて保存 コマンドを発行するときに次に示します。  
  
1.  表示、**名前を付けて保存** ダイアログ ボックスをユーザーからファイル名を取得します。  
  
2.  としてユーザーによって指定されたファイルを開き、`CFile`オブジェクト。  
  
3.  作成、`CArchive`これが指すオブジェクト`CFile`オブジェクト。 作成する、`CArchive`オブジェクト、フレームワークは、"を"保存するモードを設定 (書き込み、シリアル化)、"load"ではなく (読み取り、逆シリアル化) します。  
  
4.  呼び出し、`Serialize`関数で定義されている、 **CDocument**-派生クラスへの参照を渡す、`CArchive`オブジェクト。  
  
 ドキュメントの`Serialize`関数にデータを書き込む、`CArchive`オブジェクト、すぐに説明したようです。 戻ったとき、`Serialize`関数の場合、フレームワークの破棄、`CArchive`オブジェクトし、`CFile`オブジェクト。  
  
 したがって、フレームワークに作成できるようにする場合、`CArchive`オブジェクトをドキュメントのドキュメントの実装が行う必要があるすべて`Serialize`とアーカイブの間を読み書きする関数。 実装しなければ`Serialize`のいずれか`CObject`-派生オブジェクトをドキュメントの`Serialize`関数は、直接的または間接的にさらにシリアル化します。  
  
##  <a name="_core_explicit_creation_of_a_carchive_object"></a> CArchive オブジェクトの明示的な作成  
 フレームワークを使用してドキュメントをシリアル化する以外にもする必要があります、`CArchive`オブジェクト。 によって表される、クリップボードからデータをシリアル化するなど、`CSharedFile`オブジェクト。 または、フレームワークによって提供されるものとは異なるファイルの保存用ユーザー インターフェイスを使用することがあります。 この例では、明示的に作成できます、`CArchive`オブジェクト。 これを行うために、フレームワークは、同じ方法、次の手順を使用します。  
  
#### <a name="to-explicitly-create-a-carchive-object"></a>CArchive オブジェクトを明示的に作成するには  
  
1.  構築、`CFile`から派生したオブジェクトまたはオブジェクト`CFile`です。  
  
2.  渡す、`CFile`オブジェクトのコンス トラクターを`CArchive`次の例のように。  
  
     [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]  
  
     2 番目の引数、`CArchive`コンス トラクターは、アーカイブを格納する、またはデータの読み込み、ファイルから用に使用するかどうかを指定する列挙値。 `Serialize`オブジェクトの関数が呼び出すことによってこの状態を調べ、`IsStoring`アーカイブ オブジェクトの関数。  
  
 格納するかとの間のデータの読み込みが完了したら、`CArchive`オブジェクトを閉じます。 ただし、 `CArchive` (および`CFile`) オブジェクトが自動的を閉じて、アーカイブ (ファイル)、エラーから回復に簡単には、明示的に行うことをお勧めします。 エラー処理の詳細については、記事を参照してください。[例外: 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)です。  
  
#### <a name="to-close-the-carchive-object"></a>CArchive オブジェクトをクローズするには  
  
1.  次の例を終了する方法を示しています、`CArchive`オブジェクト。  
  
     [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)

