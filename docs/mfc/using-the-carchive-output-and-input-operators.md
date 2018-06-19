---
title: 使用して、CArchive &lt; &lt;と&gt;&gt;演算子 |Microsoft ドキュメント
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
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82b729caaa650fde72741497d3f4ab3c131f46ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383333"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>使用して、CArchive &lt; &lt;と&gt;&gt;演算子
`CArchive` 提供 <\<と >> 単純なデータ型の読み書きの演算子だけでなく`CObject`ファイルとの間の秒。  
  
#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>アーカイブを通じたファイルにオブジェクトを格納するには  
  
1.  次の例では、アーカイブを通じたファイルにオブジェクトを格納する方法を示します。  
  
     [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]  
  
#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>ファイルに格納されていた値からオブジェクトを読み込む  
  
1.  次の例では、ファイルに格納されていた値からオブジェクトを読み込む方法を示します。  
  
     [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]  
  
 通常は、格納し、データのアーカイブを通じたファイルから読み込む、`Serialize`関数の`CObject`-派生クラスで宣言されている必要がありますが、**読み込んだり**マクロです。 参照、`CArchive`にオブジェクトが渡される、`Serialize`関数。 呼び出す、`IsLoading`の関数、`CArchive`を決定するオブジェクトかどうか、`Serialize`ファイルからデータを読み込んだり、ファイルにデータを格納する関数が呼び出されました。  
  
 `Serialize`のシリアル化可能な関数`CObject`-派生クラスは、次の形式を通常は。  
  
 [!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]  
  
 上記のコード テンプレートまったく同じである AppWizard は作成の 1 つとして、`Serialize`ドキュメントの機能 (から派生したクラス**CDocument)** です。 このテンプレート コードでは、ファイルを格納するコードと読み込みのコードは常に次の例のように、並列ためにを確認して、簡単なコードを記述できます。  
  
 [!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]  
  
 ライブラリ、定義**< \<** と**>>** 演算子`CArchive`最初のオペランドと、次のデータ型と 2 番目のオペランドとしてクラス型として:  
  
||||  
|-|-|-|  
|`CObject*`|**サイズと CSize**|**float**|  
|**WORD**|`CString`|**ポイント**と `CPoint`|  
|`DWORD`|**BYTE**|`RECT` および `CRect`|  
|**Double**|**LONG**|`CTime` および `CTimeSpan`|  
|`Int`|**COleCurrency**|`COleVariant`|  
|`COleDateTime`|`COleDateTimeSpan`||  
  
> [!NOTE]
>  格納と読み込み`CObject`アーカイブを通じた s は注意が必要です。 詳細については、次を参照してください。[の保存とアーカイブを通じた Cobject の読み込み](../mfc/storing-and-loading-cobjects-via-an-archive.md)です。  
  
 **CArchive <\<** と**>>** 演算子は常にへの参照を返す、`CArchive`最初のオペランドであるオブジェクト。 これにより、演算子のチェーンを以下に示すよう。  
  
 [!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)

