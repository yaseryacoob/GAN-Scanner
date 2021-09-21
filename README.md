## This is a list of software components completed by UMD

| Analytic  | Type  | Target | Evidence Type | Status |
| :------------ |:---------------|:-----|:-----|:-----|
| [sri-umd-yydeepfakedetection](https://gitlab.semaforprogram.com/semafor/teams/ta1/sri/umd/yydeepfakedetection)  | Detection | Video | No evidence | Complete|
| [sri-umd-yyvideoinpaintinggpu](https://gitlab.semaforprogram.com/semafor/teams/ta1/sri/umd/yyvideoinpaintinggpu) | Detection        |   Video | Video of masked areas| Missing AAG| 
| [sri-umd-ssimagecaption](https://gitlab.semaforprogram.com/semafor/teams/ta1/sri/umd/ssimagecaption) | Detection | Image/Caption consistency | No evidence|AOM-DOC to be checked|
| [sri-umd-yyimagesplicegsrnet](https://gitlab.semaforprogram.com/semafor/teams/ta1/sri/umd/yyimagesplicegsrnet)| Detection|Images| A mask with likelyhood of tampering of pixels|AAG Spatial Evidence|
| [sri-umd-sgganattribution](https://gitlab.semaforprogram.com/semafor/teams/ta1/sri/umd/sgganattribution) | Detection        | Images | Attribution to a GAN or Real Dataset |Complete|
| [sri-umd-yydetectgangpu](https://gitlab.semaforprogram.com/semafor/teams/ta1/sri/umd/yydetectgangpu)| Detection| Images | No Evidence |Complete|
| [sri-umd-yylatentgan](https://gitlab.semaforprogram.com/semafor/teams/ta1/sri/umd/yylatentgan)|Detection|Images|Image returned as Evidence|Missing AAG|

## Analytics tests

All Analytcs can be tested on probes, such as 

<font size="-4">
semafor-test-harness probe sri-umd-yyimagesplicegsrnet  /home/yaser/semafor/datalake/default/ag/1ede6de0e14e84623bb0663361b375d9f44e9db4.json

semafor-test-harness probe sri-umd-yyimagesplicegsrnet  /home/yaser/semafor/datalake/default/ag/36bdee76d6d2f9ffbbd00b111e386d7edfee92ba-ag.json

semafor-test-harness probe sri-umd-yyimagesplicegsrnet  /home/yaser/semafor/datalake/default/ag/3d9edc00d9de8c9342cc145d4073a0974b6edee2-ag.json

semafor-test-harness probe sri-umd-yyimagesplicegsrnet  /home/yaser/semafor/datalake/default/ag/6e2f770432cd50907b677bb1c4af8cb64dfddbd5-ag.json

semafor-test-harness probe sri-umd-yyimagesplicegsrnet  /home/yaser/semafor/datalake/default/ag/7867dd3d6c61a1a0ac1700a78724bf74a21e52e0-ag.json

semafor-test-harness probe sri-umd-yyimagesplicegsrnet  /home/yaser/semafor/datalake/default/ag/79a0e8aa8b7b18c82ca4ab9d7aac63bf075655a1-ag.json

semafor-test-harness probe sri-umd-yyimagesplicegsrnet  /home/yaser/semafor/datalake/default/ag/b300bb079fc63f538065e24006d4f2c4075d3450-ag.json

semafor-test-harness probe sri-umd-yyimagesplicegsrnet  /home/yaser/semafor/datalake/default/ag/faf8dcdde7744173f1eb54b26802d2f1ffd8ec3f-ag.json
</font>

## Take into account:

1. Make changes in the folder where the json is
2. Analytic name
3. Analytics are currently raising an exception instead of an optout (so no issue if you see error as a response, look at the log)
4. GPU analytics are first in line for testing, these are (yyvideoinpaintinggpu, yydetectgangpu and yylatentgan). The rest are CPU-based

## Example Evidence Graphs

### DeepFake Detector
<img src="./deepfake.png">


### GAN Attribution (note there is evidence in the EvidenceNode, provided as a label)
<img src="./ganattribution.png">

### GAN Detection, best for faces but reports on all images
<img src="./yygangpu.png">


### Splicing Detection- GSRNet
<img src="./gsrnet.png">


### Image/Caption Consistency
<img src="./ssimagecaption.png">

### Video INpinating Detection
<img src="./videoinpainting.png">

### Latentgan StyleGAN2
<img src="./latentgan.png">



