---
description: 詳細については、「CArchive オブジェクトとは」を参照してください。
title: CArchive オブジェクトとは
ms.date: 11/04/2016
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
ms.openlocfilehash: 7d98200f87f4b428a9450894aca5f8958115d627
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142793"
---
# <a name="what-is-a-carchive-object"></a>CArchive オブジェクトとは

オブジェクトは、オブジェクトとの `CArchive` 間でシリアル化可能なオブジェクトを読み書きするためのタイプセーフなバッファリング機構を提供し `CFile` ます。 通常、 `CFile` オブジェクトはディスクファイルを表しますが、メモリファイル (オブジェクト) である場合もあり `CSharedFile` ます。これは、おそらくクリップボードを表します。

特定のオブジェクトは、データ `CArchive` の格納 (書き込み、シリアル化) または読み込み (読み取り、逆シリアル化) のいずれかを行いますが、両方を行うことはありません。 オブジェクトの有効期間は、オブジェクトを `CArchive` ファイルに書き込むかファイルからオブジェクトを読み取ることによって、1つのパスに制限されます。 したがって、データを `CArchive` ファイルにシリアル化し、ファイルから逆シリアル化するために、2つのオブジェクトが連続して作成されている必要があります。

アーカイブでオブジェクトがファイルに格納されている場合、アーカイブによってオブジェクトに名前が添付され `CRuntimeClass` ます。 その後、別のアーカイブがオブジェクトをファイルからメモリに読み込むと、 `CObject` オブジェクトのに基づいて、から派生したオブジェクトが動的に再構築され `CRuntimeClass` ます。 指定されたオブジェクトは、保存アーカイブによってファイルに書き込まれるため、複数回参照される可能性があります。 ただし、読み込みアーカイブでは、オブジェクトが1回だけ再構築されます。 アーカイブがオブジェクトに情報をアタッチし、オブジェクトを再構築する方法の詳細については、複数の参照を考慮して、「 `CRuntimeClass` [テクニカルノート 2](../mfc/tn002-persistent-object-data-format.md)」で説明されています。

データがアーカイブにシリアル化されると、アーカイブはバッファーがいっぱいになるまでデータを蓄積します。 次に、このアーカイブは、 `CFile` オブジェクトが指すオブジェクトにバッファーを書き込み `CArchive` ます。 同様に、アーカイブからデータを読み取ると、ファイルからバッファーにデータを読み取り、バッファーから逆シリアル化されたオブジェクトにデータを読み込みます。 このバッファリングにより、ハードディスクが物理的に読み取られる回数が少なくなるため、アプリケーションのパフォーマンスが向上します。

## <a name="see-also"></a>関連項目

[シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)
