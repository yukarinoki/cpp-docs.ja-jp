---
title: 名前ではなく序数値による DLL 関数のエクスポート
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions [C++], ordinal values
- ordinal exports [C++]
- exporting DLLs [C++], ordinal values
- NONAME attribute
ms.assetid: 679719fd-d965-4df3-9f7a-7d86ad831702
ms.openlocfilehash: 66e99b18d181e9067e90398c35a61db2da66c301
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328572"
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>名前ではなく序数値による DLL 関数のエクスポート

DLL から関数をエクスポートする最も簡単な方法は、名前でエクスポートすることです。 これは、たとえば **__declspec(dllexport)** を使用する場合に発生します。 しかし、関数を序数でエクスポートすることもできます。 この方法では **、__declspec (dllexport)** の代わりに .def ファイルを使用する必要があります。 関数の序数を指定するには、.def ファイルの関数名に序数を追加します。 序数の指定については[、「.def ファイルを使用した DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)」を参照してください。

> [!TIP]
> DLL のファイル サイズを最適化する場合は、エクスポートされた各関数に対して**NONAME**属性を使用します。 **NONAME**属性を指定すると、序数は関数名ではなく、DLL のエクスポート テーブルに格納されます。 多くの関数をエクスポートする場合、これは大幅に節約できます。

## <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください

- [序数でエクスポートできるように .def ファイルを使用する](exporting-from-a-dll-using-def-files.md)

- [__declspecを使用する(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](exporting-from-a-dll.md)
