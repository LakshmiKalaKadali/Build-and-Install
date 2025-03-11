```mermaid
flowchart TB
    subgraph Components
        model["Model Layer (example_model.py)"]
        data["Data Layer (example_input.py)"]
        task["Task Layer (example_task.py)"]
        config["Config Layer (example_config.py)"]
    end

    subgraph Model
        exmodel["ExampleModel\n(tf.keras.Model)"]
        build_model["build_example_model()"]
    end

    subgraph DataLoader
        decoder["Decoder\n(decoder.Decoder)"]
        parser["Parser\n(parser.Parser)"]
        inputreader["InputReader"]
    end

    subgraph Task
        extask["ExampleTask\n(ImageClassificationTask)"]
        buildmodel["build_model()"]
        buildinputs["build_inputs()"]
        buildlosses["build_losses()"]
        buildmetrics["build_metrics()"]
        trainstep["train_step()"]
        valstep["validation_step()"]
    end

    subgraph Config
        dataconfig["ExampleDataConfig"]
        modelconfig["ExampleModelConfig"]
        lossconfig["LossConfig"]
        evalconfig["EvaluationConfig"]
        taskconfig["ExampleTaskConfig"]
        expconfig["tf_vision_example_experiment()"]
    end

    subgraph Training
        registry["registry_imports.py"]
        train["train.py"]
    end

    model --> exmodel
    model --> build_model
    data --> decoder
    data --> parser
    decoder --> inputreader
    parser --> inputreader
    
    task --> extask
    extask --> buildmodel
    extask --> buildinputs
    extask --> buildlosses
    extask --> buildmetrics
    extask --> trainstep
    extask --> valstep
    
    config --> dataconfig
    config --> modelconfig
    config --> lossconfig
    config --> evalconfig
    config --> taskconfig
    config --> expconfig
    
    expconfig --> train
    registry --> train
    
    buildmodel --> exmodel
    buildinputs --> inputreader
    
    dataconfig --> taskconfig
    modelconfig --> taskconfig
    lossconfig --> taskconfig
    evalconfig --> taskconfig
    taskconfig --> expconfig
