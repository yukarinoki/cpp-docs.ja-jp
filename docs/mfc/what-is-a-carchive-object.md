---
title: CArchive オブジェクトとは
ms.date: 11/04/2016
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
ms.openlocfilehash: 0a78385c81c43a4b0c925bbe89ccd3937873ee8b
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446016"
---
# <a name="what-is-a-carchive-object"></a>CArchive オブジェクトとは

`CArchive` オブジェクトは、`CFile` オブジェクトとの間でシリアル化可能なオブジェクトを読み書きするためのタイプセーフなバッファリング機構を提供します。 通常、`CFile` オブジェクトはディスクファイルを表します。ただし、メモリファイル (`CSharedFile` オブジェクト) である場合もあります。これはクリップボードを表します。

指定された `CArchive` オブジェクトは、データの格納 (書き込み、シリアル化) または読み込み (読み取り、逆シリアル化) のいずれかを行いますが、両方を行うことはありません。 `CArchive` オブジェクトの有効期間は、オブジェクトをファイルに書き込むかファイルからオブジェクトを読み取ることによって、1つのパスに制限されます。 したがって、データをファイルにシリアル化してファイルから逆シリアル化するには、2つの `CArchive` オブジェクトが連続して作成されている必要があります。

アーカイブでオブジェクトがファイルに格納されている場合、アーカイブによって `CRuntimeClass` 名がオブジェクトにアタッチされます。 その後、別のアーカイブがオブジェクトをファイルからメモリに読み込むと、オブジェクトの `CRuntimeClass` に基づいて、`CObject`派生オブジェクトが動的に再構築されます。 指定されたオブジェクトは、保存アーカイブによってファイルに書き込まれるため、複数回参照される可能性があります。 ただし、読み込みアーカイブでは、オブジェクトが1回だけ再構築されます。 アーカイブによってオブジェクトに `CRuntimeClass` 情報がアタッチされ、オブジェクトが再構築される方法の詳細については、「[テクニカルノート 2](../mfc/tn002-persistent-object-data-format.md)」を参照してください。

データがアーカイブにシリアル化されると、アーカイブはバッファーがいっぱいになるまでデータを蓄積します。 次に、このアーカイブは、`CArchive` オブジェクトが指す `CFile` オブジェクトにバッファーを書き込みます。 同様に、アーカイブからデータを読み取ると、ファイルからバッファーにデータを読み取り、バッファーから逆シリアル化されたオブジェクトにデータを読み込みます。 このバッファリングにより、ハードディスクが物理的に読み取られる回数が少なくなるため、アプリケーションのパフォーマンスが向上します。

## <a name="see-also"></a>参照

[シリアル化: オブジェクトのシリアル化](../mfc/serialization-serializing-an-object.md)
