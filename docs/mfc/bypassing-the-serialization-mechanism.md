---
description: 詳細については、「シリアル化機構のバイパス」を参照してください。
title: シリアル化機構のバイパス
ms.date: 11/04/2016
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
ms.openlocfilehash: 18d31267ca2dd7760daa839556790af26ff38f6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339775"
---
# <a name="bypassing-the-serialization-mechanism"></a>シリアル化機構のバイパス

既に説明したように、フレームワークには、ファイルとの間でデータを読み書きするための既定の方法が用意されています。 Archive オブジェクトによるシリアル化は、多くのアプリケーションのニーズに適しています。 このようなアプリケーションでは、ファイル全体がメモリに読み込まれ、ユーザーがファイルを更新して、更新されたバージョンを再びディスクに書き込むことができます。

ただし、アプリケーションによっては、データがまったく異なる方法で処理されるものもあれば、アーカイブによってシリアル化されるアプリケーションに適していないものもあります。 たとえば、データベースプログラム、大きなファイルの一部のみを編集するプログラム、テキストのみのファイルを書き込むプログラム、データファイルを共有するプログラムなどがあります。

このような場合は、[シリアル化](reference/cobject-class.md#serialize)関数を別の方法でオーバーライドして、 [CArchive](reference/carchive-class.md)オブジェクトではなく[CFile](reference/cfile-class.md)オブジェクトを使用してファイルアクションを仲介することができます。

`Open` `Read` `Write` クラスの、、、 `Close` 、およびの各メンバー関数を使用して、ファイルを開き、ファイル `Seek` `CFile` ポインター (seek) をファイル内の特定の位置に移動し、その時点でレコード (指定されたバイト数) を読み取り、ユーザーがレコードを更新してから、そのレコードを再びファイルに書き戻すことができます。 フレームワークによってファイルが開き、 `GetFile` クラスのメンバー関数を使用して `CArchive` 、オブジェクトへのポインターを取得でき `CFile` ます。 さらに洗練された柔軟な使用方法として、クラスの [Onopendocument](reference/cdocument-class.md#onopendocument) および [onsavedocument](reference/cdocument-class.md#onsavedocument) メンバー関数をオーバーライドでき `CWinApp` ます。 詳細については、 *MFC リファレンス* の「クラス [CFile](reference/cfile-class.md) 」を参照してください。

このシナリオでは、 `Serialize` 上書きによって何も実行されません。ただし、たとえば、ドキュメントを閉じるときに最新の状態に保つためにファイルヘッダーを読み書きする必要がある場合は除きます。

## <a name="see-also"></a>関連項目

[ドキュメントの使用](using-documents.md)
