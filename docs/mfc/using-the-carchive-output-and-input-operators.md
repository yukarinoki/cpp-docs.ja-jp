---
title: CArchive &lt;&lt; と &gt;&gt; 演算子の使用
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: 8e175f35f2218341c69571c818711596180df4a6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442175"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>CArchive &lt;&lt; と &gt;&gt; 演算子の使用

`CArchive` には、単純なデータ型の書き込みと読み取り、およびファイルとの > を行うための <\< および > の `CObject`演算子が用意されています。

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>アーカイブを介してファイルにオブジェクトを格納するには

1. 次の例は、アーカイブを介してファイルにオブジェクトを格納する方法を示しています。

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>以前にファイルに格納されていた値からオブジェクトを読み込むには

1. 次の例は、以前にファイルに格納されていた値からオブジェクトを読み込む方法を示しています。

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

通常は、`CObject`派生クラスの `Serialize` 関数内のアーカイブを使用して、ファイルとの間でデータを格納し、読み込むことができます。この場合、DECLARE_SERIALIZE マクロを使用して宣言する必要があります。 `CArchive` オブジェクトへの参照が `Serialize` 関数に渡されます。 `CArchive` オブジェクトの `IsLoading` 関数を呼び出して、ファイルからデータを読み込むかファイルにデータを格納するために `Serialize` 関数が呼び出されたかどうかを判断します。

シリアル化可能な `CObject`派生クラスの `Serialize` 関数には、通常、次の形式があります。

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

上記のコードテンプレートは、ドキュメントの `Serialize` 関数 (`CDocument`から派生したクラス) 用に作成されたものとまったく同じです。 このコードテンプレートを使用すると、次の例に示すように、格納するコードと読み込みコードを常に並列処理する必要があるため、確認しやすいコードを記述できます。

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

このライブラリでは、最初のオペランドとして `CArchive` に使用する **<の \<** と **>>** 演算子、および2番目のオペランドとして次のデータ型とクラス型を定義します。

||||
|-|-|-|
|`CObject*`|**サイズ**と `CSize`|**float**|
|**WORD**|`CString`|**ポイント**と `CPoint`|
|`DWORD`|**BYTE**|`RECT` および `CRect`|
|**Double**|**LONG**|`CTime` および `CTimeSpan`|
|`Int`|**COleCurrency**|`COleVariant`|
|`COleDateTime`|`COleDateTimeSpan`||

> [!NOTE]
>  アーカイブを介して `CObject`s を格納して読み込むには、追加の考慮事項が必要です。 詳細については、[アーカイブを使用した通じた cobject の格納と読み込み](../mfc/storing-and-loading-cobjects-via-an-archive.md)に関する記述を参照してください。

**CArchive <\<** および **>>** 演算子は、常に、最初のオペランドである `CArchive` オブジェクトへの参照を返します。 これにより、次に示すように、演算子を連鎖させることができます。

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>参照

[シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)
