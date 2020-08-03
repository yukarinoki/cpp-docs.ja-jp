---
title: Visual C++ の 64 ビットへの移行に関する一般的な問題
ms.date: 05/06/2019
helpviewer_keywords:
- 64-bit programming [C++], migration
- 64-bit compiler [C++], migration
- porting 32-bit code to 64-bit code
- migration [C++], 64-bit code issues
- 32-bit code porting [C++]
- 64-bit applications [C++]
- 64-bit compiler [C++], porting 32-bit code
- Win64 [C++]
ms.assetid: d17fb838-7513-4e2d-8b27-a1666f17ad76
ms.openlocfilehash: 68f4dc4276c5cbce687477ca25ec69f0cb544acb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229858"
---
# <a name="common-visual-c-64-bit-migration-issues"></a>Visual C++ の 64 ビットへの移行に関する一般的な問題

Microsoft C++ コンパイラ (MSVC) を使用して、64 ビット Windows オペレーティング システムで実行するアプリケーションを作成する場合は、以下の点を考慮する必要があります。

- **`int`** と **`long`** は、64 ビット Windows オペレーティング システム上で 32 ビット値です。 64 ビット プラットフォーム用にコンパイルする必要があるプログラムでは、ポインターを 32 ビット変数に割り当てないように注意してください。 ポインターは、64 ビットのプラットフォームでは 64 ビットなので、ポインターを 32 ビット変数に割り当てると、ポインター値を切り捨てることになります。

- `size_t`、`time_t`、および `ptrdiff_t` は、64 ビット Windows オペレーティング システム上で 64 ビット値です。

- `time_t` は、Visual Studio 2005 以前の 32 ビット Windows オペレーティング システムでは 32 ビット値です。 現在は、`time_t` は既定で 64 ビット整数です。 詳細については、「[時間管理](../c-runtime-library/time-management.md)」を参照してください。

   コード内で **`int`** 値を使用する場所について、およびその値を `size_t` または `time_t` のどちらの値として処理するかについて考慮する必要があります。 32 ビットよりも大きくなると、 **`int`** ストレージに返されるときにデータが切り捨てられます。

%x (16 進数 **`int`** 形式) `printf` 修飾子は、64 ビット Windows オペレーティング システム上では期待どおりに動作しません。 この修飾子は、渡された値の最初の 32 ビットしか操作しません。

- 32 ビット整数型を 16 進数形式で表示するには、%I32x を使用します。

- 64 ビット整数型を 16 進数形式で表示するには、%I64x を使用します。

- %p (ポインターに対応する 16 進数形式) は、64 ビット Windows オペレーティング システム上で期待どおりに動作します。

詳細については次を参照してください:

- [MSVC コンパイラ オプション](reference/compiler-options.md)

- [移行に関するヒント](/windows/win32/WinProg64/migration-tips)

## <a name="see-also"></a>関連項目

[64 ビットの x64 ターゲット用に C++ プロジェクトを構成する](configuring-programs-for-64-bit-visual-cpp.md)<br/>
[Visual C++ 移植とアップグレードのガイド](../porting/visual-cpp-porting-and-upgrading-guide.md)
