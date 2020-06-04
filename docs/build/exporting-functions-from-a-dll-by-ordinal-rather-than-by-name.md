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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328572"
---
# <a name="exporting-functions-from-a-dll-by-ordinal-rather-than-by-name"></a>名前ではなく序数値による DLL 関数のエクスポート

DLL から関数をエクスポートするもっとも単純な方法は、名前によるエクスポートです。 これは、たとえば **__declspec(dllexport)** を使用した場合に発生します。 ただし、代わりに序数で関数をエクスポートできます。 この手法では、 **__declspec(dllexport)** ではなく、.def ファイルを使用する必要があります。 関数の序数値を指定するには、その序数を .def ファイル内の関数名に追加します。 序数の指定の詳細については、「[.def ファイルを使用した DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)」を参照してください。

> [!TIP]
> DLL のファイルサイズを最適化する場合は、エクスポートされる各関数に対して **NONAME** 属性を使用します。 **NONAME** 属性を使用すると、序数が関数名ではなく DLL のエクスポート テーブルに格納されます。 多くの関数をエクスポートする場合、これは大幅な節約になる可能性があります。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [序数でエクスポートできるように .def ファイルを使用する](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) を使用する](exporting-from-a-dll-using-declspec-dllexport.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](exporting-from-a-dll.md)
