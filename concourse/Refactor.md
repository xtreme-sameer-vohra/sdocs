# Principles


# Nomenclature

- *Artifact* Concourse abstraction for binary objects that need to be stored & retrived in order to execute steps, jobs and pipelines. Agnostic of Runtime Storage.
- *ArtifactSource* The complementary object associated with an *Artifact* that stores and retrieves the binary objects needed by Concourse. Implements the streaming functionality. Implemented by each Runtime Storage.

# TODOs
Steps defined in `exec` should not reference `volumes`
  - `artifact_input_step`
  - `artifact_output_step`
  
  
FetchSourceFactory shouldn't depend on dbResourceCacheFactory OR it should only perform read operations on ResourceCache state in the DB and should be only responsible for fetching images and storing them. The responsiblity of updating the associated metadata regarding the ResourceCache should be decoupled

Determine relationship between a Step and Resources. Currently, the Steps leverage the Resources, However, that results in Core to Runtime control needing to pass back and forth. For example, a `Get Step`, does some client(worker) stuff and then gives control to Resource, which is a Core abstraction, when then calls RunScript which goes back to Runtime. Is there a different way of organizing this to reduce the complexity.


# Questions
1. Where is volume's ID determined ?

   /atc/db/volume_repository -> createVolume generates a uuid