---
title: CSocketFile クラス
ms.date: 11/04/2016
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
ms.openlocfilehash: f3fa73320ae34283b0cdac559111a53a879c031c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274272"
---
# <a name="csocketfile-class"></a>CSocketFile クラス

Windows ソケットを使ったネットワーク間でのデータの送受信に使われる `CFile` オブジェクトです。

## <a name="syntax"></a>構文

```
class CSocketFile : public CFile
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSocketFile::CSocketFile](#csocketfile)|`CSocketFile` オブジェクトを構築します。|

## <a name="remarks"></a>Remarks

アタッチすることができます、`CSocketFile`オブジェクトを`CSocket`この目的のオブジェクト。 できるアプリと接続には、通常、`CSocketFile`オブジェクトを`CArchive`MFC のシリアル化を使用してデータの送受信を簡略化するオブジェクト。

(送信) データをシリアル化するに挿入することを呼び出すと、アーカイブ`CSocketFile`データを書き込むメンバー関数、`CSocket`オブジェクト。 逆シリアル化する (受信) アーカイブからデータを抽出します。 これにより、アーカイブを呼び出す`CSocketFile`メンバー関数からデータを読み取る、`CSocket`オブジェクト。

> [!TIP]
>  使用するだけでなく`CSocketFile`ここで説明したとおり、として使用できますが、スタンドアロンのファイル オブジェクトと同様`CFile`、その基本クラス。 使用することも`CSocketFile`すべてアーカイブ ベースの MFC のシリアル化関数とします。 `CSocketFile`すべてのサポートされない`CFile`機能、MFC の既定のシリアル化の関数と互換性がない`CSocketFile`します。 これは特に、`CEditView`クラス。 シリアル化しないでください`CEditView`を使用してデータを`CArchive`オブジェクトにアタッチされて、`CSocketFile`オブジェクトを使用して`CEditView::SerializeRaw`; を使用して、`CEditView::Serialize`代わりにします。 `SerializeRaw`関数に必要なファイル オブジェクトなど、関数に`Seek`、その`CSocketFile`はありません。

使用すると`CArchive`で`CSocketFile`と`CSocket`、状況が発生する可能性があります、`CSocket::Receive`ループに入る (によって`PumpMessages(FD_READ)`) バイトの要求された時間待機しています。 これは Windows sockets FD_READ 通知ごとに 1 つだけ受信呼び出しを許可するためですが、`CSocketFile`と`CSocket`FD_READ ごとの複数の受信呼び出しを許可します。 読み取るデータがない場合に、FD_READ が発生した場合、アプリケーションがハングします。 別の FD_READ 取得しない場合、アプリケーションはソケット通信を停止します。

次のように、この問題を解決できます。 `OnReceive`メソッドを呼び出し、socket クラスの`CAsyncSocket::IOCtl(FIONREAD, ...)`を呼び出す前に、`Serialize`ソケットから読み取ることが予想されるデータが 1 つの TCP パケットのネットワークのメディア (最大転送単位のサイズを超えるとメッセージ クラスのメソッド、通常は、少なくとも 1096 バイト)。 使用可能なデータのサイズが小さいと、必要以上の場合は、すべてのデータを受信して、読み取り操作を開始してから、待機します。

次の例では、`m_dwExpected`は、ユーザーが受信するバイトのおおよその数です。 宣言している他の場所で、コードと見なされます。

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

詳細については、次を参照してください。 [MFC における Windows ソケット](../../mfc/windows-sockets-in-mfc.md)、 [Windows ソケット。アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)、だけでなく[Windows Sockets 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxsock.h

##  <a name="csocketfile"></a>  CSocketFile::CSocketFile

`CSocketFile` オブジェクトを構築します。

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>パラメーター

*pSocket*<br/>
アタッチするソケット、`CSocketFile`オブジェクト。

*bArchiveCompatible*<br/>
ファイル オブジェクトで使用するかどうかを指定する`CArchive`オブジェクト。 パスを使用する場合にのみ FALSE、`CSocketFile`を単独でオブジェクトのスタンドアロンどおり`CFile`オブジェクトは、制限事項があります。 このフラグを変更する方法、`CArchive`オブジェクトにアタッチされて、`CSocketFile`オブジェクトが読み取り用には、そのバッファーを管理します。

### <a name="remarks"></a>Remarks

オブジェクトのデストラクターの関連付けを解除自体ソケット オブジェクトから、オブジェクトがスコープ外になるか、削除時にします。

> [!NOTE]
>  A`CSocketFile`なし (制限あり) ファイルとしても使用できます、`CArchive`オブジェクト。 既定で、`CSocketFile`コンス トラクターの*で*パラメーターは TRUE です。 これは、アーカイブと使用のファイル オブジェクトであることを指定します。 FALSE を渡す、アーカイブせずに、ファイル オブジェクトを使用する、*で*パラメーター。

その「アーカイブ互換性のある」モードで、`CSocketFile`オブジェクト パフォーマンスが向上し、「デッドロック」の危険性は減少 デッドロックは、送信側と受信側の両方のソケットは、互いのまたは一般的なリソースを待機しているときに発生します。 場合に、このような状況が発生する可能性があります、`CArchive`と協力して、オブジェクト、`CSocketFile`と同様、`CFile`オブジェクト。 `CFile`アーカイブの場合、要求したバイト数、受信ファイルの末尾に達したことを想定できます。

`CSocketFile`、ただし、データは、メッセージ ベース; バッファーは、複数のメッセージを含めることができます、要求されたバイト数よりも少ないのため受信ファイルの終わりを意味しません。 アプリケーションでは、それほどで、ここではブロックされません`CFile`バッファーが空になるまで、バッファーからメッセージの読み取りを続けます。 [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty)関数は、このような場合、アーカイブのバッファーの状態を監視するために役立ちます。

使用の詳細については`CSocketFile`、記事を参照して[Windows ソケット。アーカイブ付きソケットの使用](../../mfc/windows-sockets-using-sockets-with-archives.md)と[Windows ソケット。アーカイブを使用するソケットの例](../../mfc/windows-sockets-example-of-sockets-using-archives.md)します。

## <a name="see-also"></a>関連項目

[CFile クラス](../../mfc/reference/cfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket クラス](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocket クラス](../../mfc/reference/csocket-class.md)
