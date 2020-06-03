---
title: CArchive&lt;&lt;と演算子&gt;&gt;の使用
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: 91ea565867cc0cb3b27ad9d5597037b637cb6544
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368963"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>CArchive&lt;&lt;と演算子&gt;&gt;の使用

`CArchive`には、\<単純なデータ型の書き込みと読み取`CObject`り、およびファイルとの間の s の読み込みに対する<演算子と >> 演算子が用意されています。

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>アーカイブを使用してオブジェクトをファイルに保存するには

1. 次の例は、アーカイブを介してオブジェクトをファイルに格納する方法を示しています。

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>ファイルに格納されている値からオブジェクトを読み込むには

1. 次の例は、ファイルに格納されている値からオブジェクトを読み込む方法を示しています。

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

通常、DECLARE_SERIALIZE マクロで宣言した必要がある -derived クラスの`Serialize``CObject`関数で、アーカイブを介してファイルとの間でデータを格納したり読み込む場合があります。 `CArchive`オブジェクトへの参照が関数に渡されます`Serialize`。 オブジェクトの関数`IsLoading`を`CArchive`呼び出して、ファイルから`Serialize`データを読み込むか、ファイルにデータを格納するために関数が呼び出されたかどうかを確認します。

シリアル`Serialize`化可能な`CObject`派生クラスの関数は、通常、次の形式を持ちます。

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

上記のコード テンプレートは、AppWizard がドキュメントの関数 (`Serialize`から`CDocument`派生したクラス) に対して作成するテンプレートとまったく同じです。 このコード テンプレートを使用すると、次の例のように、格納コードと読み込みコードは常に並列であるため、確認しやすいコードを記述できます。

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

ライブラリは、**<** 第**>>** 1`CArchive`オペランドとして、および次のデータ型とクラス型を第 2 オペランドとして定義し、演算子を定義します。

||||
|-|-|-|
|`CObject*`|**サイズ**と`CSize`|**float**|
|**単語**|`CString`|**ポイント**と`CPoint`|
|`DWORD`|**バイト**|`RECT` および `CRect`|
|**Double**|**長い**|`CTime` および `CTimeSpan`|
|`Int`|**COleCurrency**|`COleVariant`|
|`COleDateTime`|`COleDateTimeSpan`||

> [!NOTE]
> アーカイブ経由で`CObject`の s の保存と読み込みには、追加の考慮事項が必要です。 詳細については、「[アーカイブを使用した CObject の保存とロード」を参照](../mfc/storing-and-loading-cobjects-via-an-archive.md)してください。

**CArchive <\<** と**>>** 演算子は、常に最初の`CArchive`オペランドであるオブジェクトへの参照を返します。 これにより、次に示すように演算子をチェーンすることができます。

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>関連項目

[シリアル化 : オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)
