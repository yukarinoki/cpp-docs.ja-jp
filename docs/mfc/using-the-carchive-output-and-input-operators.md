---
title: CArchive &lt; &lt; と &gt; &gt; 演算子の使用
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: 0351cd0fad1d0fc838c75d3cdbd809a04b0fb393
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832296"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>CArchive &lt; &lt; と &gt; &gt; 演算子の使用

`CArchive` ファイルとの \< and > 間で簡単なデータ型の書き込みと読み取りを行うための <> 演算子を提供し `CObject` ます。

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>アーカイブを介してファイルにオブジェクトを格納するには

1. 次の例は、アーカイブを介してファイルにオブジェクトを格納する方法を示しています。

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>以前にファイルに格納されていた値からオブジェクトを読み込むには

1. 次の例は、以前にファイルに格納されていた値からオブジェクトを読み込む方法を示しています。

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

通常は、から派生したクラスの関数のアーカイブを使用して、ファイルとの間でデータを格納し、読み込むことができます。この場合、 `Serialize` `CObject` DECLARE_SERIALIZE マクロを使用して宣言する必要があります。 オブジェクトへの参照 `CArchive` が関数に渡され `Serialize` ます。 `IsLoading`オブジェクトの関数を呼び出し `CArchive` て、 `Serialize` ファイルからデータを読み込んだり、データをファイルに格納したりするために関数が呼び出されたかどうかを判断します。

`Serialize`シリアル化可能な派生クラスの関数には、 `CObject` 通常、次の形式があります。

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

上記のコードテンプレートは、 `Serialize` ドキュメント (から派生したクラス) の関数に対して AppWizard で作成したものとまったく同じです `CDocument` 。 このコードテンプレートを使用すると、次の例に示すように、格納するコードと読み込みコードを常に並列処理する必要があるため、確認しやすいコードを記述できます。

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

このライブラリでは **`<<`** 、1番目のオペランドとしてと演算子を定義し、 **`>>`** `CArchive` 次のデータ型とクラス型を2番目のオペランドとして定義します。

:::row:::
   :::column span="":::
      `BYTE`\
      `CObject*`\
      `COleCurrency`\
      `COleDateTime`\
      `COleDateTimeSpan`
   :::column-end:::
   :::column span="":::
      `COleVariant`\
      `CString`\
      `CTime` と `CTimeSpan`\
      `Double`
   :::column-end:::
   :::column span="":::
      `DWORD`\
      `Float`\
      `Int`\
      `LONG`
   :::column-end:::
   :::column span="":::
      `POINT` と `CPoint`\
      `RECT` と `CRect`\
      `SIZE` と `CSize`\
      `WORD`
   :::column-end:::
:::row-end:::

> [!NOTE]
> アーカイブを使用して s を格納して読み込む `CObject` には、別途考慮が必要です。 詳細については、 [アーカイブを使用した通じた cobject の格納と読み込み](../mfc/storing-and-loading-cobjects-via-an-archive.md)に関する記述を参照してください。

`CArchive` **`<<`** および演算子は、 **`>>`** 常に、最初のオペランドであるオブジェクトへの参照を返し `CArchive` ます。 これにより、次に示すように、演算子を連鎖させることができます。

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>関連項目

[シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)
